This is explained in the JLS 14.20.3.2 Extended try-with-resources :

The meaning of an extended try-with-resources statement:

try ResourceSpecification
    Block
Catchesopt
Finallyopt
is given by the following translation to a basic try-with-resources statement (§14.20.3.1) nested inside a try-catch or try-finally or try-catch-finally statement:

try {
    try ResourceSpecification
        Block
}
Catchesopt
Finallyopt
The effect of the translation is to put the ResourceSpecification "inside" the try statement. This allows a catch clause of an extended try-with-resources statement to catch an exception due to the automatic initialization or closing of any resource.

Furthermore, all resources will have been closed (or attempted to be closed) by the time the finally block is executed, in keeping with the intent of the finally keyword.


https://stackoverflow.com/questions/57305586/compiled-class-problem-in-java-try-catch-block
