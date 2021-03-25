1. When yoo create a function to return JSX , dont forget to use the return statement.

2. React Frafment - A common pattern in React is for a component to return multiple elements. Fragments let you group a list of children without adding extra nodes to the DOM.


3. Apply some styling to the Table componet

4. Drawback of Style Components- Cant use Psedu selectors an media queries 
	npm install --save Radium
	- can be used in both class based component and functional component
	
	import Radium from 'radium'
	
	const style = {
    color : 'blue',
    ':hover' : {
        color:'green',
    }
}

5. npm install --save prop-types

	Usage - 
	
6. class component 
	 event handler 
	 
	  constructor(props){
        super(props)
        this.state = {
            'counter' : 0
        }
    }
	 
	 <button style= {{color:'blue'}} onClick={this.incrementHandler.bind(this)}>Increment</button>
	 
	  incrementHandler = (counter) => {
        this.setState({
            'counter' : counter + 1
        })
        console.log(this.state.counter)
    }
	
7. Functional Components-
	
	 const [counter, setCounter] = useState(0)

    const incrementHanler = (event, counter) =>{
        setCounter((counter)=>{
            return(
                counter + 1
            )
        })
        console.log(`clicked `, counter)
    }

    const resetHandler =  () => {
        setCounter(()=>{
            return 0
        })
    }
	
	<button onClick={(event)=>incrementHanler(event,counter)}>Increment</button>
	
8. JSX - 
	 return React.createElement('div',{style:{color:'red'}},React.createElement('h1',null,'This is Working'))
	 
9. Functional based Components - 

10. Class based Components - 

11. Higher Order Componnets - 

12. Component LifeCycle

	componentDidMount(){
        this.setState({
            counter: 3
        })
    }
	
	componentDidUpdate(){
        console.log("Component Unmounted")
    }
	
	 shouldComponentUpdate(){
        if (this.state.counter >= 15){
            return false
        }
        else {
            return true
        }
    }
	
13. LazyLoading

	const LazyTableComponent = lazy(() => import('../components/Table'))
	
13. Routing

import React from 'react'

	import {BrowserRouter as Router } from 'react-router-dom'
	import Route from 'react-router-dom/Route'

	const User = (props) => {
		return(
		<div>Hi! {props.match.params.username}</div>
		)
	}

	export default User
	
	<Router>
    <div className="App">
      <Route path='/' exact>
        <div>This is Home Page</div>
      </Route>

      <Route path='/about' exact>
        <div>This is About Page</div>
      </Route>

      <Route path='/user/:username' exact component={User}></Route>

      <ul>
        <li>
          <Link to='/'>Home Page</Link>
        </li>
        <li>
          <Link to='/about'>About Page</Link>
        </li>
        <li>
          <Link to='/user/:Peter'>User</Link>
        </li>
      </ul>
      
    </div>
    </Router>
	
	