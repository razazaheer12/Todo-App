# ✅ Todo App

A sleek, modern, and fully responsive **Todo App** that helps you stay organized and productive. Add tasks, track your progress, filter by status, and manage your daily to-dos effortlessly — all with a beautiful purple-themed interface and persistent local storage.

<p align="center">
  <a href="https://todo-app-2001.netlify.app/" target="_blank">
    <img src="https://img.shields.io/badge/Live%20Demo-View%20Site-brightgreen?style=for-the-badge&logo=netlify" alt="Live Demo" />
  </a>
  <a href="https://github.com/razazaheer12/Todo-App" target="_blank">
    <img src="https://img.shields.io/badge/GitHub-Repository-blue?style=for-the-badge&logo=github" alt="GitHub Repo" />
  </a>
</p>

---

## 📸 Preview

[Todo App Preview](<img width="820" height="395" alt="image" src="https://github.com/user-attachments/assets/4ebe4b2f-84b0-465e-9dfb-ad43edea978f" />
)

> **Live URL:** [https://todo-app-2001.netlify.app/](https://todo-app-2001.netlify.app/)

---

## ✨ Features

| Feature | Description |
|---------|-------------|
| ➕ **Add Tasks** | Quickly add new tasks using the input field or by pressing the Enter key. |
| ✅ **Mark Complete** | Toggle tasks between active and completed with a smooth custom checkbox. |
| 🗑️ **Delete Tasks** | Remove individual tasks with a single click — delete button appears on hover. |
| 🔍 **Filter Tasks** | Switch between All, Active, and Completed views to focus on what matters. |
| 🧹 **Clear Completed** | Remove all completed tasks at once with the "Clear completed" button. |
| 📊 **Items Counter** | Live counter showing how many uncompleted tasks remain. |
| 📅 **Current Date** | Displays today's date in the header for better context. |
| 💾 **Local Storage** | All tasks persist in your browser — no data lost on refresh or restart. |
| 📱 **Fully Responsive** | Works beautifully on desktops, tablets, and mobile devices. |
| 🎨 **Modern UI** | Clean purple gradient design with smooth transitions and hover effects. |
| 📭 **Empty State** | Friendly message and icon displayed when no tasks are present. |

---

## 🛠️ Tech Stack

<p align="left">
  <img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" alt="HTML5" />
  <img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white" alt="CSS3" />
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" alt="JavaScript" />
  <img src="https://img.shields.io/badge/Font%20Awesome-528DD7?style=for-the-badge&logo=fontawesome&logoColor=white" alt="Font Awesome" />
  <img src="https://img.shields.io/badge/Netlify-00C7B7?style=for-the-badge&logo=netlify&logoColor=white" alt="Netlify" />
</p>

- **HTML5** — Semantic structure with accessible form elements
- **CSS3** — Modern styling with CSS variables, Flexbox, custom checkboxes, transitions, and responsive design
- **Vanilla JavaScript** — Pure DOM manipulation, event handling, and localStorage API
- **Font Awesome** — Beautiful icons for UI elements (check circle, plus, times, clipboard)
- **Netlify** — Fast and reliable static site hosting

---

## 🚀 Getting Started

### Prerequisites

You only need a modern web browser to run this project locally. No build tools, frameworks, or dependencies required!

### Installation

1. **Clone the repository**

   ```bash
   git clone https://github.com/razazaheer12/Todo-App.git
   ```

2. **Navigate to the project folder**

   ```bash
   cd Todo-App
   ```

3. **Open in browser**

   Simply open the `index.html` file in your favorite browser:

   ```bash
   # On Windows
   start index.html

   # On macOS
   open index.html

   # On Linux
   xdg-open index.html
   ```

   Or use a live server extension in VS Code for the best development experience.

---

## 📖 How to Use

1. **Add a Task** — Type your task in the input field and click the **+** button (or press **Enter**).
2. **Complete a Task** — Click the checkbox next to any task to mark it as done. The text will be struck through.
3. **View Filtered Tasks** — Use the **All**, **Active**, or **Completed** tabs to filter your task list.
4. **Delete a Task** — Hover over a task and click the **×** icon to remove it.
5. **Clear Completed** — Click the **Clear completed** button at the bottom to remove all finished tasks at once.
6. **Track Progress** — The "items left" counter shows how many tasks are still pending.
7. **Persistent Data** — Your tasks are saved automatically in your browser's local storage. Close and reopen — your list will still be there!

---

## 📁 Project Structure

```
Todo-App/
│
├── index.html          # Main HTML structure
├── style.css           # All styles, CSS variables, custom checkbox, and responsive queries
├── script.js           # Application logic, localStorage, DOM rendering, and event handling
└── README.md           # Project documentation
```

### File Overview

| File | Purpose |
|------|---------|
| `index.html` | Defines the app layout including header with date, task input, filter tabs, todo list, and footer. |
| `style.css` | Provides a modern purple-themed design with CSS variables, custom animated checkboxes, hover effects, and responsive styling. |
| `script.js` | Handles all interactivity: adding/deleting/toggling tasks, filtering views, calculating item counts, persisting data to `localStorage`, and date display. |

---

## 🎯 Key Functionalities

### Adding a Task
```javascript
function addTodo(text) {
  if (text.trim() === "") return;

  const todo = {
    id: Date.now(),
    text,
    completed: false,
  };

  todos.push(todo);
  saveTodos();
  renderTodos();
  taskInput.value = "";
}
```

### Toggling Completion
```javascript
function toggleTodo(id) {
  todos = todos.map((todo) => {
    if (todo.id === id) {
      return { ...todo, completed: !todo.completed };
    }
    return todo;
  });
  saveTodos();
  renderTodos();
}
```

### Filtering Tasks
```javascript
function filterTodos(filter) {
  switch (filter) {
    case "active":
      return todos.filter((todo) => !todo.completed);
    case "completed":
      return todos.filter((todo) => todo.completed);
    default:
      return todos;
  }
}
```

### Data Persistence
```javascript
function saveTodos() {
  localStorage.setItem("todos", JSON.stringify(todos));
  updateItemsCount();
  checkEmptyState();
}

function loadTodos() {
  const storedTodos = localStorage.getItem("todos");
  if (storedTodos) todos = JSON.parse(storedTodos);
  renderTodos();
}
```

---

## 📱 Responsive Design

The application is fully responsive and adapts seamlessly to all screen sizes:

- **Desktop (500px+)** — Centered card layout with maximum width for comfortable reading.
- **Tablet & Mobile** — Flexible layout with full-width input, optimized tap targets, and preserved styling.
- **Touch-Friendly** — Buttons and checkboxes are sized appropriately for touch interaction.

---

## 🎨 Design Highlights

- 💜 **Purple Theme** — Elegant purple (`#7749f8`) primary color representing focus and creativity.
- ✅ **Custom Checkbox** — Beautiful animated checkbox with a green checkmark and smooth transitions.
- ✨ **Hover Interactions** — Delete button appears smoothly on hover; list items highlight on hover.
- 🎯 **Active Filters** — Underlined active filter tab for clear visual indication.
- 📭 **Empty State** — Friendly clipboard icon with "No tasks here yet" message when the list is empty.
- 🗑️ **Clear Completed** — Subtle danger-red hover effect on the clear button for destructive action.

---

## 🔮 Future Enhancements

- [ ] Edit existing tasks inline
- [ ] Drag and drop to reorder tasks
- [ ] Task categories or tags
- [ ] Due dates and reminders
- [ ] Priority levels (high, medium, low)
- [ ] Dark mode toggle
- [ ] Task search functionality
- [ ] Export task list to text or JSON
- [ ] Cloud sync with user authentication
- [ ] Progress bar or completion percentage

---

## 🤝 Contributing

Contributions are welcome! If you have suggestions, bug fixes, or new features to add:

1. Fork the repository
2. Create a new branch (`git checkout -b feature/YourFeature`)
3. Commit your changes (`git commit -m 'Add some feature'`)
4. Push to the branch (`git push origin feature/YourFeature`)
5. Open a Pull Request

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

## 🙏 Acknowledgments

- Built with ❤️ by [Raza Zaheer](https://github.com/razazaheer12)
- Hosted on [Netlify](https://www.netlify.com/)
- Icons by [Font Awesome](https://fontawesome.com/)

---

<p align="center">
  <b>⭐ Star this repo if you found it helpful!</b>
</p>

<p align="center">
  <a href="https://todo-app-2001.netlify.app/">🌐 Live Demo</a> •
  <a href="https://github.com/razazaheer12/Todo-App">💻 GitHub Repo</a>
</p>

