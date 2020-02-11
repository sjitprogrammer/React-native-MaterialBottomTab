# React-native-MaterialBottomTab
work at 12/2/2020

install dependencies

    "@react-native-community/masked-view": "^0.1.6",
    "@react-navigation/bottom-tabs": "^5.0.2",
    "@react-navigation/drawer": "^5.0.1",
    "@react-navigation/material-bottom-tabs": "^5.0.1",
    "@react-navigation/native": "^5.0.1",
    "@react-navigation/native-stack": "^5.0.2",
    "@react-navigation/stack": "^5.0.2",
    "react": "16.9.0",
    "react-native": "0.61.5",
    "react-native-gesture-handler": "^1.5.6",
    "react-native-paper": "^3.6.0",
    "react-native-reanimated": "^1.7.0",
    "react-native-safe-area-context": "^0.7.2",
    "react-native-screens": "^2.0.0-beta.2",
    "react-native-tab-view": "^2.13.0",
    "react-native-vector-icons": "^6.6.0"
    
example App.js
<img src="https://github.com/sjitprogrammer/React-native-MaterialBottomTab/blob/master/Screenshot_1581448614.png" width="300"
    
    import * as React from 'react';
    import { Text, View } from 'react-native';
    import { NavigationContainer } from '@react-navigation/native';
    import { createMaterialBottomTabNavigator } from '@react-navigation/material-bottom-tabs';
    import { MaterialCommunityIcons } from 'react-native-vector-icons/MaterialCommunityIcons';
    import FontAwesome from "react-native-vector-icons/FontAwesome5";

    function Feed() {
      return (
        <View style={{ flex: 1, justifyContent: 'center', alignItems: 'center' }}>
          <Text>Feed!</Text>
        </View>
      );
    }
    function Saved() {
      return (
        <View style={{ flex: 1, justifyContent: 'center', alignItems: 'center' }}>
          <Text>Saved!</Text>
        </View>
      );
    }
    function Trips() {
      return (
        <View style={{ flex: 1, justifyContent: 'center', alignItems: 'center' }}>
          <Text>Trips!</Text>
        </View>
      );
    }
    function Inbox() {
      return (
        <View style={{ flex: 1, justifyContent: 'center', alignItems: 'center' }}>
          <Text>Inbox!</Text>
        </View>
      );
    }
    function Profile() {
      return (
        <View style={{ flex: 1, justifyContent: 'center', alignItems: 'center' }}>
          <Text>Profile!</Text>
        </View>
      );
    }



    const Tab = createMaterialBottomTabNavigator();

    function MyTabs() {
      return (
        <Tab.Navigator
          initialRouteName="Feed"
          activeColor="#e91e63"
          inactiveColor="#000000"
          labelStyle={{ fontSize: 12 }}
          barStyle={{backgroundColor:'#ffffff'}}
        >
          <Tab.Screen
            name="Feed"
            component={Feed}
            options={{
              tabBarLabel: 'Explore',
              tabBarIcon: ({ color, size }) => (
                <FontAwesome name="search" color={color} size={24} />
              ),
            }}
          />
          <Tab.Screen
            name="Saved"
            component={Saved}
            options={{
              tabBarLabel: 'Saved',
              tabBarIcon: ({ color, size }) => (
                <FontAwesome name="heart" color={color} size={24} />
              ),
            }}
          />
          <Tab.Screen
            name="Trips"
            component={Trips}
            options={{
              tabBarLabel: 'Trips',
              tabBarIcon: ({ color, size }) => (
                <FontAwesome name="instagram" color={color} size={24} />
              ),
            }}
          />
          <Tab.Screen
            name="Inbox"
            component={Inbox}
            options={{
              tabBarLabel: 'Inbox',
              tabBarIcon: ({ color, size }) => (
                <FontAwesome name="comment-alt" color={color} size={24} />
              ),
            }}
          />
          <Tab.Screen
            name="Profile"
            component={Profile}
            options={{
              tabBarLabel: 'Profile',
              tabBarIcon: ({ color, size }) => (
                <FontAwesome name="user" color={color} size={24} />
              ),
            }}
          />
        </Tab.Navigator>
      );
    }

    export default class App extends React.Component{
      render(){
        return (
          <NavigationContainer>
            <MyTabs />
          </NavigationContainer>
        );
      }
    }

