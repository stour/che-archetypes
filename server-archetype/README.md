# Maven archetype to generate a new server extension for Eclipse Che
This utility will generate a Che plug-in that deploys a REST service on Che.

This follows the tutorial that is provided at http://eclipse.org/che.

# License
This project is licensed as EPL 1.0.

# Clone & build the archetype
    git clone https://github.com/stour/server-extension-archetype
    mvn clean install

# Use the archetype to generate a new plug-in
    mvn archetype:generate -DarchetypeCatalog=local -DarchetypeGroupId=org.eclipse.che.archetype -DarchetypeArtifactId=che-server-extension-archetype -DinteractiveMode=false
This will generate a new plugin using default values for `groupId`, `artifactId`, `version`, `package` and `yourPrefix`.
Value of `yourPrefix` will be used as a prefix to name the files of your new plug-in. This property needs to be a value that can generate valid Java classes.
If you want to choose your own values for these properties simply execute the same command in interactive mode.

# Compile your new plug-in
    cd {your_plugin_name}
    mvn clean install

# Add your plug-in to Che
1. [Copy the JAR](https://eclipse-che.readme.io/v1.0/docs/plug-ins#add-plug-in-by-copying-jar-file) to Che , or:
2. [Reference the JAR] (https://eclipse-che.readme.io/v1.0/docs/plug-ins#add-plug-in-by-referencing-jar-file)

If you reference the JAR, the artifactId, groupId, and version properties provided must be the values used when updating the Che pom.xml.
