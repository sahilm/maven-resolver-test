# Maven Resolver Test

# What do I want to do?

* Given a POM file on the local filesystem
* I want to programmatically obtain the effective POM of that POM file. Specifically I want to do the following:
  * Resolve the POMs dependencies
  * Ensure that all parent POMs are processed
  * Obtain the list of dependencies of the fully resolved POM
  * And so on...

* I don't need to obtain transitive dependencies.

# What works?

I'm using [Maven Resolver Provider](https://maven.apache.org/ref/3.6.0/maven-resolver-provider/) which works. However
I have to use a package private class `org.apache.maven.repository.internal.DefaultModelResolver`

There's an example program which does the following:

* Downloads the latest spring boot POM from Maven Central.
* Prints out it's direct dependencies (with parent deps included) 

You can run the the program with:
`mvn exec:java -Dexec.mainClass="com.sahilm.maven_resolver_test.Test"`

# What I need help with?

* I need help with understanding why I have to use a package private class to get stuff to work.
* Is there another way to get the information I need?
