Hibernate
=========

Hibernate is an excellent Object Relational Mapper. Using just xml files, we are able to describe the relationship between all of our tables and our domain (POJO) objects (like Patient.java, Concept.java, etc). Looking at the concept domain in the datamodel, we see that it consists of tables named concept, concept_answer, concept_set, concept_name. It would be very difficult to keep up with where to store each part of the concept object and the relations between them. Using Hibernate, we only need to concern ourselves with the Concept object, not the tables behind the object. The concept.hbm.xml mapping file does the hard work of knowing that the Concept object contains a collection of ConceptSet objects, a collection of ConceptName objects, etc. To add a new name to a concept:

    ConceptService conceptService = Context.getConceptService();
    