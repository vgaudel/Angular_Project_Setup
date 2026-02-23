# Creating Your First Angular Project

## Prerequisites

Before getting started, ensure you have the following installed on your system:

- **Node.js** (v18 or higher recommended): [Download here](https://nodejs.org/)
- **npm** (comes with Node.js): Verify with `npm -v`

Check your versions:
```bash
node --version
npm --version
```

---

## Step 1: Install Angular CLI

Angular CLI is a command-line tool that simplifies Angular project creation and development.

```bash
npm install -g @angular/cli
```

Verify the installation:
```bash
ng version
```

---

## Step 2: Create a New Angular Project

Run the following command to generate a new Angular project:

```bash
ng new my-first-app
```

When prompted, you'll be asked several questions:

- **Would you like to add Angular routing?** → `Yes` (for multi-page apps)
- **Which stylesheet format would you like to use?** → Choose CSS, SCSS, LESS, or Sass
- **Do you want to enable Server-Side Rendering (SSR)?** → `Yes` or `No` (depending on your needs)

This creates a project folder with all necessary files and dependencies.

---

## Step 3: Navigate to Your Project

```bash
cd my-first-app
```

---

## Step 4: Run the Development Server

```bash
ng serve
```

or with auto-reload:

```bash
ng serve --open
```

The application will be available at `http://localhost:4200/`

---

## Project Structure Overview

```
my-first-app/
├── src/
│   ├── app/
│   │   ├── app.component.html    # Main component template
│   │   ├── app.component.css     # Component styles
│   │   ├── app.component.ts      # Component logic
│   │   ├── app.routes.ts         # Routing configuration
│   │   └── ...
│   ├── index.html                # Main HTML file
│   ├── main.ts                   # Application entry point
│   └── styles.css                # Global styles
├── angular.json                  # Angular CLI configuration
├── package.json                  # Project dependencies
├── tsconfig.json                 # TypeScript configuration
└── README.md                      # Project documentation
```

---

## Key Files Explained

### `src/main.ts` - Application Entry Point
```typescript
// The first file executed when your app starts
import { bootstrapApplication } from '@angular/platform-browser';
import { AppComponent } from './app/app.component';

bootstrapApplication(AppComponent);
```

### `src/app/app.component.ts` - Main Component
```typescript
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  standalone: true,
  templateUrl: './app.component.html',
  styleUrl: './app.component.css'
})
export class AppComponent {
  title = 'my-first-app';
}
```

### `src/app/app.component.html` - Component Template
```html
<h1>Welcome to {{ title }}!</h1>
```

---

## Basic Angular Concepts

### Components
A component is the basic building block of Angular applications. It consists of:
- **Template** (.html) - The UI
- **Styles** (.css) - Styling
- **Class** (.ts) - Logic

Create a new component:
```bash
ng generate component components/my-component
```

### Services
Services provide shared functionality across components.

```bash
ng generate service services/my-service
```

### Directives
Built-in directives for common tasks:
- `*ngIf` - Conditional rendering
- `*ngFor` - Loop through arrays
- `[ngClass]` - Dynamically add CSS classes

### Data Binding
- **Interpolation**: `{{ variable }}`
- **Property Binding**: `[property]="value"`
- **Event Binding**: `(click)="method()"`
- **Two-Way Binding**: `[(ngModel)]="variable"`

### Routing
Configure routes in `app.routes.ts`:
```typescript
import { Routes } from '@angular/router';
import { HomeComponent } from './components/home/home.component';
import { AboutComponent } from './components/about/about.component';

export const routes: Routes = [
  { path: '', component: HomeComponent },
  { path: 'about', component: AboutComponent }
];
```

---

## Common Commands

```bash
# Generate new component
ng generate component component-name
ng g c component-name  # Short syntax

# Generate new service
ng generate service service-name
ng g s service-name

# Generate new module
ng generate module module-name
ng g m module-name

# Run tests
ng test

# Build for production
ng build

# Build with server-side rendering
ng build --prerender
```

---

## Building for Production

```bash
ng build --configuration production
```

This creates an optimized version in the `dist/` folder ready for deployment.

---

## Useful Resources

- [Official Angular Documentation](https://angular.io/docs)
- [Angular CLI Documentation](https://angular.io/cli)
- [Angular Tutorial](https://angular.io/tutorial)
- [Angular API Reference](https://angular.io/api)

---

## Next Steps

1. **Create your first component** to replace the default app component
2. **Set up routing** for navigation between pages
3. **Build services** for data management
4. **Connect to an API** using HttpClient
5. **Deploy your application**

Happy coding! 🚀
