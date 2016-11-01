# Warpwire Sakai 10 Install Instructions
For more visit: warpwire.com or contact us: support@warpwire.net

The steps to add the Warpwire Sakai plugin to a Sakai 10 instance are as follows:

1. Within the tomcat installation directory (default directory is /opt/tomcat, but may be different for your configuration), locate the <tomcat-installation-directory>/sakai/sakai.properties file, and append the following line to the portal.include.extrahead property within the file:

     ```<script type="text/javascript" src="/library/js/warpwire.js"></script>```
     
    It is possible that the portal.include.extrahead property is not set in the properties file in your installation - in this case, simply append the following line to the sakai.properties file instead:

     ```portal.include.extrahead=<script type="text/javascript" src="/library/js/warpwire.js"></script>```
     
2. Within the <tomcat-installation-directory>/sakai directory, create a folder named 'portlets', if it does not already exist (Resulting folder location will be <tomcat-installation-directory>/sakai/portlets)

3. Copy the IMSBLTIPortlet.xml file (located at xml/IMSBLTIPortlet.xml in the included archive) into the folder from the previous step (<tomcat-installation-location>/sakai/portlets).  This is the xml configuration file that allows the Warpwire plugin to exist as an LTI tool within your Sakai installation.

4. Replace the ```[[WW_LAUNCH_URL]]```, ```[[WW_SECRET]]```, and ```[[WW_CONSUMER_KEY]]``` within the newly created <tomcat-installation-location>/sakai/portlets/IMSBLTIPortlet.xml file with the applicable values provided by Warpwire.

5. Copy the 'warpwire.js' file (located at js/warpwire.js in the included archive) to the applicable location within your Sakai installation (<sakai-installation-location>/webapps/library/js/warpwire.js).

6. Copy the ‘warpwire’ directory (located within the ‘plugin’ folder) into the ckextraplugins folder within your Sakai installation (Resulting folder location will be <sakai-installation-location>/webapps/library/editor/ckextraplugins/warpwire).

7. Locate the <sakai-installation-location>/webapps/library/editor/ckeditor.launch.js file, and add the following line to the ckconfig variable within the file:

     ```warpwireURL: '[[WW_ROOT_DOMAIN]]',```
 
8. Replace the [[WW_ROOT_DOMAIN]] within the <sakai-installation-location>/webapps/library/editor/ckeditor.launch.js file with the applicable value provided by Warpwire.  An example of the necessary changes is located on line 80 of the file located at js/ckeditor.launch.js in the included archive.

9. Add 'warpwire' to the sakai.editor.enableResourceSearch array and within the addExternal plugin function in the ckeditor.launch.js file (located at <sakai-installation-location>/webapps/library/editor/ckeditor.launch.js).  An example of the changes necessary are located in the attached folder on lines 110-111 and 195-202 of the file located at js/ckeditor.launch.js in the included archive.



***Note***:  After following the provided steps, a restart of Sakai will be necessary in order for the Warpwire Site Tool to be accessible from within Sakai.










