// Import necessary libraries
import React, { useState, useEffect } from 'react';
import { View, Text, Image, StyleSheet, ScrollView } from 'react-native';

const TimeEntriesScreen = () => {
  // Simulating fetching time entries
  const [timeEntries, setTimeEntries] = useState([]);

  useEffect(() => {
    // Example of fetching time entries from a data source
    // You can replace it with actual API calls or local database fetch
    // For now, it's set to an empty array to simulate no entries.
    setTimeEntries([]);
  }, []);

  return (
    <ScrollView contentContainerStyle={styles.container}>
      {/* Check if there are no time entries */}
      {timeEntries.length === 0 ? (
        <View style={styles.emptyStateContainer}>
          <Image
            source={require('./assets/images/home-empty.png')}  // Path to your empty state image
            style={styles.emptyStateImage}
          />
          <Text style={styles.emptyStateText}>No time entries yet</Text>
        </View>
      ) : (
        <View>
          {/* Render time entries if they exist */}
          {timeEntries.map((entry, index) => (
            <View key={index} style={styles.entryContainer}>
              <Text>{entry}</Text>
            </View>
          ))}
        </View>
      )}
    </ScrollView>
  );
};

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    padding: 20,
  },
  emptyStateContainer: {
    justifyContent: 'center',
    alignItems: 'center',
    textAlign: 'center',
  },
  emptyStateImage: {
    width: 200,
    height: 200,
    marginBottom: 20,
  },
  emptyStateText: {
    fontSize: 18,
    color: '#888',
  },
  entryContainer: {
    padding: 10,
    borderBottomWidth: 1,
    borderColor: '#ddd',
  },
});

export default TimeEntriesScreen;
