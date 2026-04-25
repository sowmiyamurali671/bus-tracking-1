# Punjab Bus Tracking

A modern, responsive bus tracking application built with React and Tailwind CSS. Track Punjab buses in real-time with live locations, interactive maps, and accurate ETAs.

## 🚌 Features

### Passenger Features
- **Real-time Bus Search**: Find buses by destination with live locations
- **Interactive Maps**: View bus routes, stops, and locations on Leaflet maps
- **Location Detection**: Auto-detect current location for pickup point
- **Live ETAs**: Get accurate arrival time predictions
- **Responsive Design**: Works seamlessly on mobile, tablet, and desktop

### Driver Features
- **Driver Authentication**: Secure login system for drivers
- **Bus Connection**: Connect to assigned buses and start location tracking
- **Live Location Sharing**: Real-time GPS location updates
- **Dashboard**: Clean interface for bus management

### Admin Features
- **Admin Dashboard**: Complete administrative control panel
- **Bus Management**: Add buses, manage routes, assign devices
- **Driver Management**: Add drivers, manage credentials
- **Availability Control**: Mark buses as available/unavailable
- **Device Assignment**: Assign tracking devices to buses

## 🛠️ Technologies Used

- **Frontend**: React 18 (JavaScript only, no TypeScript)
- **Styling**: Tailwind CSS with custom design system
- **Maps**: react-leaflet (Leaflet.js)
- **Routing**: React Router DOM
- **Icons**: Lucide React
- **State Management**: React hooks and context
- **Build Tool**: Vite

## 🚀 Quick Start

### Prerequisites
- Node.js (v16 or higher)
- npm or yarn

### Installation

1. **Clone the repository**
   ```bash
   git clone <your-repo-url>
   cd punjab-bus-tracking
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Start development server**
   ```bash
   npm run dev
   ```

4. **Open your browser**
   Navigate to `http://localhost:5173`

### Production Build

```bash
npm run build
npm run preview
```

## 📱 Demo Credentials

### Driver Login
- **Username**: `gurpreet.singh` **Password**: `driver123`
- **Username**: `manpreet.kaur` **Password**: `driver456`
- **Username**: `hardeep.singh` **Password**: `driver789`

### Admin Login
- **Username**: `admin` **Password**: `admin123`
- **Username**: `supervisor` **Password**: `super123`

## 🗃️ Project Structure

```
src/
├── components/          # Reusable UI components
│   ├── Navbar.jsx      # Main navigation bar
│   ├── SearchForm.jsx  # Bus search interface
│   ├── BusCard.jsx     # Bus information cards
│   ├── BusModal.jsx    # Bus details modal with map
│   ├── LoginForm.jsx   # Reusable login form
│   ├── LocationButton.jsx  # GPS location detection
│   ├── DriverDashboard.jsx # Driver control panel
│   └── AdminDashboard.jsx  # Admin management interface
├── pages/              # Page components
│   ├── Home.jsx        # Main passenger interface
│   ├── DriverLogin.jsx # Driver authentication
│   ├── AdminLogin.jsx  # Admin authentication
│   └── NotFound.jsx    # 404 error page
├── services/           # API and WebSocket services
│   ├── api.js         # Mock API service
│   └── ws.js          # WebSocket mock service
├── data/              # Sample data
│   └── seed.js        # Bus and driver sample data
├── App.jsx            # Main app component
└── main.jsx           # Application entry point
```

## 🔧 Backend Integration

This application currently uses mock services for development. To integrate with a real backend:

### API Service Integration

1. **Update API Base URL** in `src/services/api.js`:
   ```javascript
   constructor() {
     this.baseUrl = 'https://your-api-server.com/api'; // Replace with real URL
   }
   ```

2. **Replace Mock Functions**: Look for `// TODO: Replace with actual API call` comments and implement real HTTP requests.

3. **Authentication**: Update token handling and storage as needed for your backend.

### WebSocket Integration

1. **Update WebSocket URL** in `src/services/ws.js`:
   ```javascript
   this.wsUrl = 'wss://your-websocket-server.com/ws'; // Replace with real URL
   ```

2. **Implement Real WebSocket**: Uncomment the real WebSocket implementation code and remove mock timers.

3. **Message Handling**: Adapt message formats to match your backend WebSocket protocol.

### Required Backend Endpoints

#### Authentication
- `POST /api/auth/driver/login` - Driver authentication
- `POST /api/auth/admin/login` - Admin authentication

#### Bus Operations
- `POST /api/buses/search` - Search buses by location and destination
- `GET /api/buses/:id` - Get bus details
- `GET /api/admin/buses` - Get all buses (admin)
- `POST /api/admin/buses` - Add new bus (admin)
- `PATCH /api/buses/:id/availability` - Update bus availability
- `PATCH /api/buses/:id/device` - Assign device to bus

#### Driver Operations
- `POST /api/driver/connect-bus` - Connect driver to bus
- `POST /api/driver/location` - Update driver location
- `GET /api/admin/drivers` - Get all drivers (admin)
- `POST /api/admin/drivers` - Add new driver (admin)

#### WebSocket Events
- `bus_location_update` - Real-time bus location updates
- `bus_status_change` - Bus availability changes
- `driver_connected` - Driver connection events

## 🎨 Design System

The application uses a custom design system with semantic color tokens:

### Colors
- **Primary**: Deep blue (#0B5FFF) - Main brand color
- **Accent**: Punjab green (#009688) - Success states and highlights
- **Success**: Green tones for available buses
- **Destructive**: Red tones for unavailable/error states

### Components
All components use semantic design tokens instead of hardcoded colors, ensuring consistent theming and easy customization.

## 📍 Map Configuration

The application uses Leaflet for maps with custom markers:
- **Bus Marker**: Custom blue bus icon
- **Passenger Marker**: Custom green user icon
- **Route Lines**: Dashed blue polylines
- **Stop Markers**: Standard markers for bus stops

## 🔐 Security Notes

- In production, implement proper password hashing
- Use secure token storage and transmission
- Implement rate limiting for API endpoints
- Validate all user inputs on the backend
- Use HTTPS for all communications

## 📄 License

MIT License - see LICENSE file for details

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## 📞 Support

For questions or issues, please open an issue on the repository or contact the development team.

---

**Built with ❤️ for Punjab's public transportation system**