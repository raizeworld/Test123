# Test123
Try lang 
// Get reference to the database
DatabaseReference database = FirebaseDatabase.getInstance().getReference();

// Write data
database.child("users").child("user1").setValue("John Doe");

// Read data
database.child("users").child("user1").get().addOnCompleteListener(task -> {
    if (task.isSuccessful()) {
        String name = task.getResult().getValue(String.class);
        Log.d("Firebase", "User: " + name);
    }
});
