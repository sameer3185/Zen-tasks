<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Zen Tasks</title>
  
  <!-- Tailwind CSS for styling -->
  <script src="https://cdn.tailwindcss.com"></script>
  
  <!-- Phosphor Icons for modern icons -->
  <script src="https://unpkg.com/@phosphor-icons/web"></script>

  <!-- Custom configuration for Tailwind -->
  <script>
    tailwind.config = {
      theme: {
        extend: {
          fontFamily: {
            sans: ['Inter', 'system-ui', 'sans-serif'],
          },
          colors: {
            brand: {
              50: '#f0fdf4',
              100: '#dcfce7',
              500: '#22c55e',
              600: '#16a34a',
              900: '#14532d',
            }
          }
        }
      }
    }
  </script>

  <style>
    /* Custom scrollbar for the task list */
    .custom-scrollbar::-webkit-scrollbar {
      width: 6px;
    }
    .custom-scrollbar::-webkit-scrollbar-track {
      background: #f1f5f9;
      border-radius: 8px;
    }
    .custom-scrollbar::-webkit-scrollbar-thumb {
      background: #cbd5e1;
      border-radius: 8px;
    }
    .custom-scrollbar::-webkit-scrollbar-thumb:hover {
      background: #94a3b8;
    }
    
    /* Smooth transitions for list items */
    .task-enter {
      animation: slideIn 0.3s ease-out forwards;
    }
    
    @keyframes slideIn {
      from { opacity: 0; transform: translateY(-10px); }
      to { opacity: 1; transform: translateY(0); }
    }
  </style>
</head>
<body class="bg-slate-50 min-h-screen flex items-center justify-center p-4 md:p-8 text-slate-800 antialiased">

  <!-- Main Application Card -->
  <div class="bg-white w-full max-w-md rounded-3xl shadow-[0_8px_30px_rgb(0,0,0,0.04)] overflow-hidden border border-slate-100 flex flex-col h-[80vh] max-h-[600px]">
    
    <!-- Header -->
    <header class="p-6 pb-4 border-b border-slate-100 bg-white/80 backdrop-blur-md sticky top-0 z-10">
      <div class="flex justify-between items-center mb-4">
        <div>
          <h1 class="text-2xl font-bold tracking-tight text-slate-900">Zen Tasks</h1>
          <p id="dateDisplay" class="text-sm text-slate-500 mt-1 font-medium"></p>
        </div>
        <div class="bg-brand-50 text-brand-600 p-2 rounded-2xl">
          <i class="ph-fill ph-check-circle text-2xl"></i>
        </div>
      </div>
      
      <!-- Input Area -->
      <div class="relative flex items-center mt-2">
        <input 
          type="text" 
          id="taskInput" 
          placeholder="What needs to be done?" 
          class="w-full bg-slate-50 border border-slate-200 text-slate-700 text-sm rounded-xl focus:ring-2 focus:ring-brand-500/20 focus:border-brand-500 block p-3.5 pr-12 transition-all outline-none"
        >
        <button 
          id="addTaskBtn"
          class="absolute right-2 p-2 bg-brand-500 hover:bg-brand-600 text-white rounded-lg transition-colors flex items-center justify-center focus:outline-none focus:ring-2 focus:ring-brand-500/50 shadow-sm"
          title="Add Task"
        >
          <i class="ph-bold ph-plus"></i>
        </button>
      </div>
    </header>

    <!-- Task List -->
    <main class="flex-1 overflow-y-auto p-6 custom-scrollbar bg-slate-50/50">
      <ul id="taskList" class="space-y-3">
        <!-- Tasks will be injected here via JavaScript -->
      </ul>
      
      <!-- Empty State -->
      <div id="emptyState" class="hidden flex-col items-center justify-center h-full text-center opacity-60 py-8">
        <i class="ph-duotone ph-leaf text-5xl text-slate-400 mb-3"></i>
        <p class="text-slate-500 font-medium">All caught up!</p>
        <p class="text-xs text-slate-400 mt-1">Add a task above to get started.</p>
      </div>
    </main>

    <!-- Footer -->
    <footer class="p-4 border-t border-slate-100 bg-white text-sm text-slate-500 flex justify-between items-center">
      <span id="taskCount" class="font-medium">0 tasks left</span>
      <button id="clearCompletedBtn" class="hover:text-slate-800 transition-colors focus:outline-none hidden">
        Clear completed
      </button>
    </footer>
  </div>

  <!-- Application Logic -->
  <script>
    document.addEventListener('DOMContentLoaded', () => {
      // DOM Elements
      const taskInput = document.getElementById('taskInput');
      const addTaskBtn = document.getElementById('addTaskBtn');
      const taskList = document.getElementById('taskList');
      const taskCountDisplay = document.getElementById('taskCount');
      const emptyState = document.getElementById('emptyState');
      const dateDisplay = document.getElementById('dateDisplay');
      const clearCompletedBtn = document.getElementById('clearCompletedBtn');

      // State (In-memory)
      let tasks = [
        { id: '1', text: 'Welcome to Zen Tasks! 👋', completed: false },
        { id: '2', text: 'Type a task above and hit Enter', completed: false },
        { id: '3', text: 'Click the circle to complete me', completed: true }
      ];

      // Initialize
      setTodayDate();
      renderTasks();

      // Event Listeners
      addTaskBtn.addEventListener('click', handleAddTask);
      taskInput.addEventListener('keypress', (e) => {
        if (e.key === 'Enter') handleAddTask();
      });
      clearCompletedBtn.addEventListener('click', clearCompleted);

      // Functions
      function setTodayDate() {
        const options = { weekday: 'long', month: 'short', day: 'numeric' };
        dateDisplay.textContent = new Date().toLocaleDateString('en-US', options);
      }

      function handleAddTask() {
        const text = taskInput.value.trim();
        if (text === '') return;

        const newTask = {
          id: Date.now().toString(),
          text: text,
          completed: false
        };

        tasks.unshift(newTask); // Add to beginning
        taskInput.value = '';
        renderTasks();
      }

      function toggleTask(id) {
        tasks = tasks.map(task => 
          task.id === id ? { ...task, completed: !task.completed } : task
        );
        renderTasks();
      }

      function deleteTask(id) {
        tasks = tasks.filter(task => task.id !== id);
        renderTasks();
      }

      function clearCompleted() {
        tasks = tasks.filter(task => !task.completed);
        renderTasks();
      }

      function updateFooter() {
        const activeTasks = tasks.filter(t => !t.completed).length;
        const hasCompleted = tasks.some(t => t.completed);
        
        taskCountDisplay.textContent = `${activeTasks} task${activeTasks !== 1 ? 's' : ''} left`;
        
        if (hasCompleted) {
          clearCompletedBtn.classList.remove('hidden');
        } else {
          clearCompletedBtn.classList.add('hidden');
        }
      }

      function renderTasks() {
        // Clear current list
        taskList.innerHTML = '';

        // Handle empty state
        if (tasks.length === 0) {
          emptyState.classList.remove('hidden');
          emptyState.classList.add('flex');
        } else {
          emptyState.classList.add('hidden');
          emptyState.classList.remove('flex');
          
          // Render each task
          tasks.forEach(task => {
            const li = document.createElement('li');
            li.className = `task-enter group flex items-center justify-between p-4 bg-white rounded-2xl border ${task.completed ? 'border-transparent shadow-sm' : 'border-slate-100 shadow-[0_2px_10px_rgb(0,0,0,0.02)]'} transition-all duration-200`;
            
            li.innerHTML = `
              <div class="flex items-center flex-1 min-w-0 cursor-pointer" onclick="toggleTaskHandler('${task.id}')">
                <button 
                  class="flex-shrink-0 w-6 h-6 rounded-full border-2 flex items-center justify-center transition-colors mr-4 focus:outline-none
                  ${task.completed ? 'bg-brand-500 border-brand-500 text-white' : 'border-slate-300 hover:border-brand-400 text-transparent'}"
                  aria-label="Toggle completion"
                >
                  <i class="ph-bold ph-check text-xs ${task.completed ? 'opacity-100' : 'opacity-0 group-hover:opacity-20'} transition-opacity"></i>
                </button>
                <span class="truncate text-sm font-medium transition-all ${task.completed ? 'text-slate-400 line-through' : 'text-slate-700'}">
                  ${escapeHTML(task.text)}
                </span>
              </div>
              <button 
                onclick="deleteTaskHandler(event, '${task.id}')"
                class="opacity-0 group-hover:opacity-100 text-slate-300 hover:text-red-500 focus:opacity-100 transition-all p-2 rounded-lg hover:bg-red-50 focus:outline-none ml-2"
                aria-label="Delete task"
              >
                <i class="ph-bold ph-trash"></i>
              </button>
            `;
            
            taskList.appendChild(li);
          });
        }

        updateFooter();
      }

      // Handlers attached to window for inline onclick attributes
      window.toggleTaskHandler = toggleTask;
      window.deleteTaskHandler = (event, id) => {
        event.stopPropagation(); // Prevent triggering the toggle
        deleteTask(id);
      };

      // Utility to prevent XSS
      function escapeHTML(str) {
        const div = document.createElement('div');
        div.textContent = str;
        return div.innerHTML;
      }
    });
  </script>
</body>
</html>
