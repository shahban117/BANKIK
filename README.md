<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Солнечный Банк | Ваши финансы в надежных руках</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary-color: #ffc107;
            --primary-light: #fff8e1;
            --primary-dark: #ff8f00;
            --secondary-color: #795548;
            --accent-color: #ff5722;
            --light-color: #fffde7;
            --dark-color: #5d4037;
            --success-color: #4caf50;
            --danger-color: #f44336;
            --gray-color: #8d6e63;
            --border-color: #ffe082;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', system-ui, -apple-system, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #fff9c4 0%, #fffde7 100%);
            color: var(--dark-color);
            min-height: 100vh;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* Header */
        header {
            background: linear-gradient(135deg, var(--primary-color) 0%, var(--primary-dark) 100%);
            color: var(--dark-color);
            padding: 15px 0;
            box-shadow: 0 4px 12px rgba(255, 193, 7, 0.3);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 12px;
        }
        
        .logo-icon {
            width: 40px;
            height: 40px;
            background: white;
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--primary-dark);
            font-weight: bold;
            font-size: 1.2rem;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
        }
        
        .logo h1 {
            font-size: 1.6rem;
            font-weight: 700;
            color: var(--dark-color);
        }
        
        .user-info {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .user-avatar {
            width: 42px;
            height: 42px;
            border-radius: 50%;
            background: linear-gradient(135deg, var(--accent-color), #ff8a65);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: bold;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15);
        }
        
        .notification-icon {
            position: relative;
            font-size: 1.3rem;
            color: var(--dark-color);
            cursor: pointer;
        }
        
        .notification-badge {
            position: absolute;
            top: -5px;
            right: -5px;
            background-color: var(--accent-color);
            color: white;
            border-radius: 50%;
            width: 18px;
            height: 18px;
            font-size: 0.7rem;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        /* Navigation */
        nav {
            background-color: white;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.05);
            border-bottom: 1px solid var(--border-color);
        }
        
        .nav-tabs {
            display: flex;
            list-style: none;
            overflow-x: auto;
        }
        
        .nav-tabs li {
            flex: 1;
            min-width: 120px;
        }
        
        .nav-tabs a {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
            padding: 16px 20px;
            text-align: center;
            text-decoration: none;
            color: var(--gray-color);
            border-bottom: 3px solid transparent;
            transition: all 0.3s;
            font-weight: 500;
        }
        
        .nav-tabs a:hover, .nav-tabs a.active {
            color: var(--primary-dark);
            border-bottom: 3px solid var(--primary-dark);
            background-color: var(--primary-light);
        }
        
        .nav-tabs a i {
            font-size: 1.1rem;
        }
        
        /* Main Content */
        main {
            padding: 30px 0;
        }
        
        .section {
            display: none;
            background-color: white;
            border-radius: 16px;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.05);
            padding: 28px;
            margin-bottom: 30px;
            border: 1px solid var(--border-color);
        }
        
        .section.active {
            display: block;
            animation: fadeIn 0.5s ease;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .section-title {
            margin-bottom: 24px;
            padding-bottom: 16px;
            border-bottom: 1px solid var(--border-color);
            color: var(--primary-dark);
            font-size: 1.5rem;
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .section-title i {
            color: var(--primary-dark);
        }
        
        /* Dashboard */
        .welcome-banner {
            background: linear-gradient(135deg, var(--primary-color) 0%, var(--primary-dark) 100%);
            color: var(--dark-color);
            border-radius: 16px;
            padding: 24px;
            margin-bottom: 30px;
            box-shadow: 0 6px 20px rgba(255, 193, 7, 0.3);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .welcome-text h2 {
            font-size: 1.5rem;
            margin-bottom: 8px;
        }
        
        .welcome-text p {
            opacity: 0.9;
            font-size: 1rem;
        }
        
        .welcome-icon {
            font-size: 3rem;
            opacity: 0.8;
        }
        
        .accounts-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
            gap: 24px;
            margin-bottom: 30px;
        }
        
        .account-card {
            background: white;
            border-radius: 16px;
            padding: 24px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.05);
            border: 1px solid var(--border-color);
            transition: all 0.3s;
            position: relative;
            overflow: hidden;
        }
        
        .account-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 6px;
            height: 100%;
            background: linear-gradient(to bottom, var(--primary-color), var(--primary-dark));
        }
        
        .account-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.1);
        }
        
        .account-header {
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            margin-bottom: 16px;
        }
        
        .account-type {
            font-size: 1rem;
            color: var(--gray-color);
            font-weight: 500;
        }
        
        .account-icon {
            width: 40px;
            height: 40px;
            border-radius: 10px;
            background: var(--primary-light);
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--primary-dark);
            font-size: 1.2rem;
        }
        
        .balance-amount {
            font-size: 2rem;
            font-weight: 700;
            margin: 10px 0;
            color: var(--dark-color);
        }
        
        .account-number {
            color: var(--gray-color);
            font-size: 0.9rem;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        
        .account-actions {
            display: flex;
            gap: 12px;
        }
        
        .account-btn {
            background-color: var(--primary-light);
            color: var(--primary-dark);
            border: none;
            border-radius: 8px;
            padding: 10px 16px;
            font-size: 0.85rem;
            cursor: pointer;
            transition: all 0.3s;
            flex: 1;
            text-align: center;
            font-weight: 500;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 6px;
        }
        
        .account-btn:hover {
            background-color: var(--primary-color);
            color: var(--dark-color);
            transform: translateY(-2px);
        }
        
        .quick-actions {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
            gap: 16px;
            margin-top: 30px;
        }
        
        .action-btn {
            background-color: white;
            color: var(--primary-dark);
            border: 1px solid var(--border-color);
            border-radius: 12px;
            padding: 20px 15px;
            text-align: center;
            cursor: pointer;
            transition: all 0.3s;
            font-weight: 600;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 10px;
        }
        
        .action-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 15px rgba(0, 0, 0, 0.1);
            background-color: var(--primary-light);
            border-color: var(--primary-color);
        }
        
        .action-btn i {
            font-size: 1.5rem;
            color: var(--primary-dark);
        }
        
        .recent-transactions {
            margin-top: 40px;
        }
        
        .recent-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
        }
        
        .transaction-list {
            list-style: none;
        }
        
        .transaction-item {
            display: flex;
            justify-content: space-between;
            padding: 18px 0;
            border-bottom: 1px solid var(--border-color);
            transition: background-color 0.2s;
        }
        
        .transaction-item:hover {
            background-color: var(--primary-light);
            border-radius: 8px;
            padding-left: 15px;
            padding-right: 15px;
            margin: 0 -15px;
        }
        
        .transaction-info {
            display: flex;
            flex-direction: column;
        }
        
        .transaction-name {
            font-weight: 600;
            margin-bottom: 5px;
        }
        
        .transaction-date {
            font-size: 0.85rem;
            color: var(--gray-color);
            display: flex;
            align-items: center;
            gap: 6px;
        }
        
        .transaction-amount.positive {
            color: var(--success-color);
            font-weight: 700;
            font-size: 1.1rem;
        }
        
        .transaction-amount.negative {
            color: var(--danger-color);
            font-weight: 700;
            font-size: 1.1rem;
        }
        
        /* Transfer Form */
        .transfer-form {
            max-width: 500px;
        }
        
        .form-group {
            margin-bottom: 24px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 10px;
            font-weight: 500;
            color: var(--dark-color);
        }
        
        .form-control {
            width: 100%;
            padding: 14px 16px;
            border: 1px solid var(--border-color);
            border-radius: 10px;
            font-size: 1rem;
            transition: all 0.3s;
            background-color: var(--light-color);
        }
        
        .form-control:focus {
            border-color: var(--primary-color);
            outline: none;
            box-shadow: 0 0 0 3px rgba(255, 193, 7, 0.1);
            background-color: white;
        }
        
        .btn {
            background: linear-gradient(135deg, var(--primary-color) 0%, var(--primary-dark) 100%);
            color: var(--dark-color);
            border: none;
            border-radius: 10px;
            padding: 14px 28px;
            font-size: 1rem;
            cursor: pointer;
            transition: all 0.3s;
            font-weight: 600;
            box-shadow: 0 4px 12px rgba(255, 193, 7, 0.3);
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 8px;
        }
        
        .btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 18px rgba(255, 193, 7, 0.4);
        }
        
        .btn-secondary {
            background: var(--light-color);
            color: var(--dark-color);
            border: 1px solid var(--border-color);
        }
        
        .btn-secondary:hover {
            background: white;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
        }
        
        /* History */
        .history-filters {
            display: flex;
            gap: 15px;
            margin-bottom: 20px;
            flex-wrap: wrap;
        }
        
        .filter-select {
            padding: 10px 16px;
            border: 1px solid var(--border-color);
            border-radius: 8px;
            background-color: white;
            color: var(--dark-color);
            font-size: 0.9rem;
        }
        
        /* Profile */
        .profile-info {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 24px;
        }
        
        .info-card {
            background-color: white;
            border-radius: 12px;
            padding: 24px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
            border: 1px solid var(--border-color);
        }
        
        .info-card h3 {
            margin-bottom: 18px;
            color: var(--primary-dark);
            font-size: 1.2rem;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .info-item {
            margin-bottom: 14px;
            display: flex;
            justify-content: space-between;
            padding-bottom: 14px;
            border-bottom: 1px solid var(--border-color);
        }
        
        /* Deposits */
        .deposits-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }
        
        .deposit-card {
            background: white;
            border-radius: 12px;
            padding: 20px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
            border: 1px solid var(--border-color);
            transition: all 0.3s;
        }
        
        .deposit-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
        }
        
        .deposit-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
        }
        
        .deposit-name {
            font-weight: 600;
            font-size: 1.1rem;
            color: var(--primary-dark);
        }
        
        .deposit-rate {
            background: var(--primary-light);
            color: var(--primary-dark);
            padding: 5px 10px;
            border-radius: 20px;
            font-weight: 600;
            font-size: 0.9rem;
        }
        
        .deposit-details {
            margin-bottom: 20px;
        }
        
        .deposit-detail {
            display: flex;
            justify-content: space-between;
            margin-bottom: 8px;
            font-size: 0.9rem;
        }
        
        /* Modal */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            z-index: 1000;
            align-items: center;
            justify-content: center;
        }
        
        .modal.active {
            display: flex;
        }
        
        .modal-content {
            background-color: white;
            border-radius: 16px;
            width: 90%;
            max-width: 500px;
            padding: 30px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
        }
        
        .modal-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 20px;
            padding-bottom: 15px;
            border-bottom: 1px solid var(--border-color);
        }
        
        .modal-title {
            font-size: 1.3rem;
            color: var(--primary-dark);
        }
        
        .close-modal {
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--gray-color);
        }
        
        .modal-footer {
            display: flex;
            justify-content: flex-end;
            gap: 10px;
            margin-top: 20px;
            padding-top: 15px;
            border-top: 1px solid var(--border-color);
        }
        
        /* Footer */
        footer {
            background: linear-gradient(135deg, var(--dark-color) 0%, #6d4c41 100%);
            color: white;
            padding: 40px 0 20px;
            margin-top: 60px;
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 30px;
        }
        
        .footer-section h3 {
            margin-bottom: 18px;
            color: var(--primary-color);
            font-size: 1.2rem;
        }
        
        .footer-section ul {
            list-style: none;
        }
        
        .footer-section ul li {
            margin-bottom: 10px;
        }
        
        .footer-section a {
            color: #d7ccc8;
            text-decoration: none;
            transition: color 0.3s;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        
        .footer-section a:hover {
            color: var(--primary-color);
        }
        
        .footer-section a i {
            width: 16px;
        }
        
        .copyright {
            text-align: center;
            margin-top: 40px;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            color: #bcaaa4;
            font-size: 0.9rem;
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                gap: 15px;
            }
            
            .welcome-banner {
                flex-direction: column;
                text-align: center;
                gap: 15px;
            }
            
            .accounts-grid, .deposits-grid {
                grid-template-columns: 1fr;
            }
            
            .quick-actions {
                grid-template-columns: repeat(2, 1fr);
            }
            
            .nav-tabs {
                justify-content: flex-start;
            }
            
            .nav-tabs li {
                flex: none;
            }
            
            .account-actions {
                flex-direction: column;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <div class="header-content">
                <div class="logo">
                    <div class="logo-icon">СБ</div>
                    <h1>Солнечный Банк</h1>
                </div>
                <div class="user-info">
                    <div class="notification-icon">
                        <i class="far fa-bell"></i>
                        <div class="notification-badge">3</div>
                    </div>
                    <div class="user-avatar" id="userAvatar">ИИ</div>
                    <div id="userNameDisplay">Иван Иванов</div>
                </div>
            </div>
        </div>
    </header>
    
    <nav>
        <div class="container">
            <ul class="nav-tabs">
                <li><a href="#dashboard" class="nav-link active"><i class="fas fa-home"></i> Главная</a></li>
                <li><a href="#transfer" class="nav-link"><i class="fas fa-exchange-alt"></i> Переводы</a></li>
                <li><a href="#deposits" class="nav-link"><i class="fas fa-piggy-bank"></i> Вклады</a></li>
                <li><a href="#history" class="nav-link"><i class="fas fa-history"></i> История</a></li>
                <li><a href="#profile" class="nav-link"><i class="fas fa-user"></i> Профиль</a></li>
            </ul>
        </div>
    </nav>
    
    <main class="container">
        <!-- Dashboard Section -->
        <section id="dashboard" class="section active">
            <div class="welcome-banner">
                <div class="welcome-text">
                    <h2 id="welcomeMessage">Добро пожаловать, Иван!</h2>
                    <p>Ваши финансы под надежным контролем</p>
                </div>
                <div class="welcome-icon">
                    <i class="fas fa-sun"></i>
                </div>
            </div>
            
            <h2 class="section-title"><i class="fas fa-wallet"></i> Мои счета</h2>
            
            <div class="accounts-grid">
                <div class="account-card">
                    <div class="account-header">
                        <div class="account-type">Основной счет</div>
                        <div class="account-icon">
                            <i class="fas fa-landmark"></i>
                        </div>
                    </div>
                    <div class="balance-amount">25 680,50 ₽</div>
                    <div class="account-number">
                        <i class="far fa-credit-card"></i> № 4081 7810 1234 5678
                    </div>
                    <div class="account-actions">
                        <button class="account-btn transfer-btn" data-account="4081 7810 1234 5678">
                            <i class="fas fa-paper-plane"></i> Перевести
                        </button>
                        <button class="account-btn">
                            <i class="fas fa-chart-bar"></i> Детали
                        </button>
                    </div>
                </div>
                
                <div class="account-card">
                    <div class="account-header">
                        <div class="account-type">Накопительный счет</div>
                        <div class="account-icon">
                            <i class="fas fa-piggy-bank"></i>
                        </div>
                    </div>
                    <div class="balance-amount">150 250,00 ₽</div>
                    <div class="account-number">
                        <i class="far fa-credit-card"></i> № 4081 7810 8765 4321
                    </div>
                    <div class="account-actions">
                        <button class="account-btn transfer-btn" data-account="4081 7810 8765 4321">
                            <i class="fas fa-paper-plane"></i> Перевести
                        </button>
                        <button class="account-btn">
                            <i class="fas fa-chart-bar"></i> Детали
                        </button>
                    </div>
                </div>
                
                <div class="account-card">
                    <div class="account-header">
                        <div class="account-type">Кредитная карта</div>
                        <div class="account-icon">
                            <i class="fas fa-credit-card"></i>
                        </div>
                    </div>
                    <div class="balance-amount" style="color: var(--danger-color);">-12 500,00 ₽</div>
                    <div class="account-number">
                        <i class="far fa-credit-card"></i> № 5536 9137 2846 5102
                    </div>
                    <div class="account-actions">
                        <button class="account-btn transfer-btn" data-account="5536 9137 2846 5102">
                            <i class="fas fa-plus-circle"></i> Пополнить
                        </button>
                        <button class="account-btn">
                            <i class="fas fa-chart-bar"></i> Детали
                        </button>
                    </div>
                </div>
            </div>
            
            <h2 class="section-title"><i class="fas fa-bolt"></i> Быстрые действия</h2>
            
            <div class="quick-actions">
                <button class="action-btn" id="quick-transfer">
                    <i class="fas fa-paper-plane"></i>
                    <span>Перевод</span>
                </button>
                <button class="action-btn">
                    <i class="fas fa-receipt"></i>
                    <span>Оплата</span>
                </button>
                <button class="action-btn" id="quick-deposit">
                    <i class="fas fa-piggy-bank"></i>
                    <span>Вклад</span>
                </button>
                <button class="action-btn">
                    <i class="fas fa-mobile-alt"></i>
                    <span>Пополнение</span>
                </button>
                <button class="action-btn">
                    <i class="fas fa-chart-line"></i>
                    <span>Инвестиции</span>
                </button>
                <button class="action-btn">
                    <i class="fas fa-file-invoice"></i>
                    <span>Выписка</span>
                </button>
            </div>
            
            <div class="recent-transactions">
                <div class="recent-header">
                    <h2 class="section-title"><i class="fas fa-clock"></i> Последние операции</h2>
                    <a href="#history" class="btn btn-secondary nav-link" style="padding: 10px 20px;">
                        <i class="fas fa-list"></i> Вся история
                    </a>
                </div>
                <ul class="transaction-list">
                    <li class="transaction-item">
                        <div class="transaction-info">
                            <div class="transaction-name">Перевод от Петрова А.</div>
                            <div class="transaction-date">
                                <i class="far fa-calendar"></i> 15.10.2023
                            </div>
                        </div>
                        <div class="transaction-amount positive">+5 000,00 ₽</div>
                    </li>
                    <li class="transaction-item">
                        <div class="transaction-info">
                            <div class="transaction-name">Оплата за коммунальные услуги</div>
                            <div class="transaction-date">
                                <i class="far fa-calendar"></i> 12.10.2023
                            </div>
                        </div>
                        <div class="transaction-amount negative">-3 245,60 ₽</div>
                    </li>
                    <li class="transaction-item">
                        <div class="transaction-info">
                            <div class="transaction-name">Пополнение счета</div>
                            <div class="transaction-date">
                                <i class="far fa-calendar"></i> 10.10.2023
                            </div>
                        </div>
                        <div class="transaction-amount positive">+10 000,00 ₽</div>
                    </li>
                </ul>
            </div>
        </section>
        
        <!-- Transfer Section -->
        <section id="transfer" class="section">
            <h2 class="section-title"><i class="fas fa-exchange-alt"></i> Перевод средств</h2>
            
            <form class="transfer-form" id="transferForm">
                <div class="form-group">
                    <label for="fromAccount"><i class="fas fa-wallet"></i> Счет списания</label>
                    <select id="fromAccount" class="form-control" required>
                        <option value="">Выберите счет</option>
                        <option value="4081 7810 1234 5678">Основной счет (25 680,50 ₽)</option>
                        <option value="4081 7810 8765 4321">Накопительный счет (150 250,00 ₽)</option>
                    </select>
                </div>
                
                <div class="form-group">
                    <label for="toAccount"><i class="fas fa-user-friends"></i> Счет получателя</label>
                    <select id="toAccount" class="form-control" required>
                        <option value="">Выберите счет</option>
                        <option value="4081 7810 1234 5678">Основной счет (25 680,50 ₽)</option>
                        <option value="4081 7810 8765 4321">Накопительный счет (150 250,00 ₽)</option>
                        <option value="5536 9137 2846 5102">Кредитная карта (-12 500,00 ₽)</option>
                        <option value="other">Другой счет</option>
                    </select>
                </div>
                
                <div class="form-group" id="externalAccountGroup" style="display: none;">
                    <label for="externalAccount"><i class="fas fa-credit-card"></i> Номер счета получателя</label>
                    <input type="text" id="externalAccount" class="form-control" placeholder="XXXX XXXX XXXX XXXX">
                </div>
                
                <div class="form-group">
                    <label for="amount"><i class="fas fa-ruble-sign"></i> Сумма перевода</label>
                    <input type="number" id="amount" class="form-control" placeholder="0,00" min="1" required>
                </div>
                
                <div class="form-group">
                    <label for="message"><i class="fas fa-comment"></i> Сообщение получателю</label>
                    <input type="text" id="message" class="form-control" placeholder="Необязательное поле">
                </div>
                
                <button type="submit" class="btn">
                    <i class="fas fa-paper-plane"></i> Перевести средства
                </button>
            </form>
        </section>
        
        <!-- Deposits Section -->
        <section id="deposits" class="section">
            <h2 class="section-title"><i class="fas fa-piggy-bank"></i> Мои вклады</h2>
            
            <div class="deposits-grid" id="userDeposits">
                <!-- Вклады будут загружены с помощью JavaScript -->
            </div>
            
            <h2 class="section-title"><i class="fas fa-plus-circle"></i> Открыть новый вклад</h2>
            
            <div class="deposits-grid">
                <div class="deposit-card">
                    <div class="deposit-header">
                        <div class="deposit-name">Солнечный Начинающий</div>
                        <div class="deposit-rate">5.5%</div>
                    </div>
                    <div class="deposit-details">
                        <div class="deposit-detail">
                            <span>Срок:</span>
                            <span>6 месяцев</span>
                        </div>
                        <div class="deposit-detail">
                            <span>Минимальная сумма:</span>
                            <span>10 000 ₽</span>
                        </div>
                        <div class="deposit-detail">
                            <span>Пополнение:</span>
                            <span>Нет</span>
                        </div>
                        <div class="deposit-detail">
                            <span>Частичное снятие:</span>
                            <span>Нет</span>
                        </div>
                    </div>
                    <button class="btn open-deposit-btn" data-deposit="Солнечный Начинающий" data-rate="5.5">
                        <i class="fas fa-plus"></i> Открыть вклад
                    </button>
                </div>
                
                <div class="deposit-card">
                    <div class="deposit-header">
                        <div class="deposit-name">Солнечный Стандарт</div>
                        <div class="deposit-rate">6.2%</div>
                    </div>
                    <div class="deposit-details">
                        <div class="deposit-detail">
                            <span>Срок:</span>
                            <span>1 год</span>
                        </div>
                        <div class="deposit-detail">
                            <span>Минимальная сумма:</span>
                            <span>50 000 ₽</span>
                        </div>
                        <div class="deposit-detail">
                            <span>Пополнение:</span>
                            <span>Да</span>
                        </div>
                        <div class="deposit-detail">
                            <span>Частичное снятие:</span>
                            <span>Нет</span>
                        </div>
                    </div>
                    <button class="btn open-deposit-btn" data-deposit="Солнечный Стандарт" data-rate="6.2">
                        <i class="fas fa-plus"></i> Открыть вклад
                    </button>
                </div>
                
                <div class="deposit-card">
                    <div class="deposit-header">
                        <div class="deposit-name">Солнечный Премиум</div>
                        <div class="deposit-rate">7.1%</div>
                    </div>
                    <div class="deposit-details">
                        <div class="deposit-detail">
                            <span>Срок:</span>
                            <span>2 года</span>
                        </div>
                        <div class="deposit-detail">
                            <span>Минимальная сумма:</span>
                            <span>100 000 ₽</span>
                        </div>
                        <div class="deposit-detail">
                            <span>Пополнение:</span>
                            <span>Да</span>
                        </div>
                        <div class="deposit-detail">
                            <span>Частичное снятие:</span>
                            <span>Да</span>
                        </div>
                    </div>
                    <button class="btn open-deposit-btn" data-deposit="Солнечный Премиум" data-rate="7.1">
                        <i class="fas fa-plus"></i> Открыть вклад
                    </button>
                </div>
            </div>
        </section>
        
        <!-- History Section -->
        <section id="history" class="section">
            <h2 class="section-title"><i class="fas fa-history"></i> История операций</h2>
            
            <div class="history-filters">
                <select class="filter-select" id="accountFilter">
                    <option value="all">Все счета</option>
                    <option value="4081 7810 1234 5678">Основной счет</option>
                    <option value="4081 7810 8765 4321">Накопительный счет</option>
                    <option value="5536 9137 2846 5102">Кредитная карта</option>
                </select>
                
                <select class="filter-select" id="typeFilter">
                    <option value="all">Все операции</option>
                    <option value="income">Только пополнения</option>
                    <option value="outcome">Только списания</option>
                </select>
                
                <select class="filter-select" id="periodFilter">
                    <option value="all">За все время</option>
                    <option value="month">За последний месяц</option>
                    <option value="week">За последнюю неделю</option>
                </select>
            </div>
            
            <ul class="transaction-list" id="transactionHistory">
                <!-- Transactions will be loaded here by JavaScript -->
            </ul>
        </section>
        
        <!-- Profile Section -->
        <section id="profile" class="section">
            <h2 class="section-title"><i class="fas fa-user"></i> Личный кабинет</h2>
            
            <div class="profile-info">
                <div class="info-card">
                    <h3><i class="fas fa-id-card"></i> Личная информация</h3>
                    <div class="info-item">
                        <span>ФИО:</span>
                        <span id="profileName">Иван Иванов</span>
                    </div>
                    <div class="info-item">
                        <span>Дата рождения:</span>
                        <span>15.03.1985</span>
                    </div>
                    <div class="info-item">
                        <span>Телефон:</span>
                        <span>+7 (900) 123-45-67</span>
                    </div>
                    <div class="info-item">
                        <span>Email:</span>
                        <span>ivanov@example.com</span>
                    </div>
                    <button class="btn" style="margin-top: 15px; width: 100%;" id="editNameBtn">
                        <i class="fas fa-edit"></i> Изменить имя
                    </button>
                </div>
                
                <div class="info-card">
                    <h3><i class="fas fa-credit-card"></i> Банковские счета</h3>
                    <div class="info-item">
                        <span>Основной счет:</span>
                        <span>4081 7810 1234 5678</span>
                    </div>
                    <div class="info-item">
                        <span>Накопительный счет:</span>
                        <span>4081 7810 8765 4321</span>
                    </div>
                    <div class="info-item">
                        <span>Кредитная карта:</span>
                        <span>5536 9137 2846 5102</span>
                    </div>
                    <button class="btn" style="margin-top: 15px; width: 100%;">
                        <i class="fas fa-plus-circle"></i> Открыть новый счет
                    </button>
                </div>
                
                <div class="info-card">
                    <h3><i class="fas fa-shield-alt"></i> Настройки безопасности</h3>
                    <div class="info-item">
                        <span>Двухфакторная аутентификация:</span>
                        <span style="color: var(--success-color);">Включена</span>
                    </div>
                    <div class="info-item">
                        <span>Уведомления:</span>
                        <span>SMS и Email</span>
                    </div>
                    <div class="info-item">
                        <span>Последний вход:</span>
                        <span>Сегодня, 14:30</span>
                    </div>
                    <button class="btn" style="margin-top: 15px; width: 100%;">
                        <i class="fas fa-key"></i> Изменить пароль
                    </button>
                </div>
            </div>
        </section>
    </main>
    
    <!-- Edit Name Modal -->
    <div class="modal" id="editNameModal">
        <div class="modal-content">
            <div class="modal-header">
                <h3 class="modal-title">Изменение имени</h3>
                <button class="close-modal">&times;</button>
            </div>
            <div class="modal-body">
                <div class="form-group">
                    <label for="newFirstName">Имя</label>
                    <input type="text" id="newFirstName" class="form-control" value="Иван">
                </div>
                <div class="form-group">
                    <label for="newLastName">Фамилия</label>
                    <input type="text" id="newLastName" class="form-control" value="Иванов">
                </div>
            </div>
            <div class="modal-footer">
                <button class="btn btn-secondary" id="cancelEditName">Отмена</button>
                <button class="btn" id="saveName">Сохранить</button>
            </div>
        </div>
    </div>
    
    <!-- Open Deposit Modal -->
    <div class="modal" id="openDepositModal">
        <div class="modal-content">
            <div class="modal-header">
                <h3 class="modal-title" id="depositModalTitle">Открытие вклада</h3>
                <button class="close-modal">&times;</button>
            </div>
            <div class="modal-body">
                <div class="form-group">
                    <label for="depositAmount">Сумма вклада</label>
                    <input type="number" id="depositAmount" class="form-control" placeholder="Введите сумму" min="1000">
                </div>
                <div class="form-group">
                    <label for="depositSourceAccount">Счет для списания</label>
                    <select id="depositSourceAccount" class="form-control">
                        <option value="4081 7810 1234 5678">Основной счет (25 680,50 ₽)</option>
                        <option value="4081 7810 8765 4321">Накопительный счет (150 250,00 ₽)</option>
                    </select>
                </div>
                <div id="depositDetails">
                    <!-- Детали вклада будут заполнены JavaScript -->
                </div>
            </div>
            <div class="modal-footer">
                <button class="btn btn-secondary" id="cancelDeposit">Отмена</button>
                <button class="btn" id="confirmDeposit">Открыть вклад</button>
            </div>
        </div>
    </div>
    
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-section">
                    <h3>Солнечный Банк</h3>
                    <ul>
                        <li><a href="#"><i class="fas fa-info-circle"></i> О банке</a></li>
                        <li><a href="#"><i class="fas fa-newspaper"></i> Новости</a></li>
                        <li><a href="#"><i class="fas fa-briefcase"></i> Вакансии</a></li>
                        <li><a href="#"><i class="fas fa-map-marker-alt"></i> Отделения</a></li>
                    </ul>
                </div>
                
                <div class="footer-section">
                    <h3>Услуги</h3>
                    <ul>
                        <li><a href="#"><i class="fas fa-hand-holding-usd"></i> Кредиты</a></li>
                        <li><a href="#"><i class="fas fa-piggy-bank"></i> Вклады</a></li>
                        <li><a href="#"><i class="fas fa-home"></i> Ипотека</a></li>
                        <li><a href="#"><i class="fas fa-chart-line"></i> Инвестиции</a></li>
                    </ul>
                </div>
                
                <div class="footer-section">
                    <h3>Поддержка</h3>
                    <ul>
                        <li><a href="#"><i class="fas fa-question-circle"></i> Частые вопросы</a></li>
                        <li><a href="#"><i class="fas fa-phone-alt"></i> Контакты</a></li>
                        <li><a href="#"><i class="fas fa-file-invoice"></i> Тарифы</a></li>
                        <li><a href="#"><i class="fas fa-comments"></i> Обратная связь</a></li>
                    </ul>
                </div>
                
                <div class="footer-section">
                    <h3>Контакты</h3>
                    <ul>
                        <li><i class="fas fa-phone"></i> 8-800-123-45-67</li>
                        <li><i class="fas fa-envelope"></i> info@sbank.ru</li>
                        <li><i class="fas fa-map-marker-alt"></i> г. Столица, ул. Центральная, 1</li>
                        <li>
                            <a href="#" style="display: inline-flex; margin-right: 15px;"><i class="fab fa-vk"></i></a>
                            <a href="#" style="display: inline-flex; margin-right: 15px;"><i class="fab fa-telegram"></i></a>
                            <a href="#" style="display: inline-flex;"><i class="fab fa-youtube"></i></a>
                        </li>
                    </ul>
                </div>
            </div>
            
            <div class="copyright">
                &copy; 2023 Солнечный Банк. Лицензия ЦБ РФ № 1234. Все права защищены.
            </div>
        </div>
    </footer>
    
    <script>
        // Данные приложения
        const accounts = {
            "4081 7810 1234 5678": {
                type: "Основной счет",
                balance: 25680.50,
                currency: "₽"
            },
            "4081 7810 8765 4321": {
                type: "Накопительный счет",
                balance: 150250.00,
                currency: "₽"
            },
            "5536 9137 2846 5102": {
                type: "Кредитная карта",
                balance: -12500.00,
                currency: "₽"
            }
        };
        
        let userData = {
            firstName: "Иван",
            lastName: "Иванов"
        };
        
        let deposits = [
            {
                id: 1,
                name: "Солнечный Начинающий",
                amount: 50000,
                rate: 5.5,
                term: 6,
                startDate: "2023-08-15",
                endDate: "2024-02-15"
            }
        ];
        
        let transactions = [
            { id: 1, from: "4081 7810 8765 4321", to: "4081 7810 1234 5678", amount: 5000, date: "2023-10-15", description: "Перевод между счетами" },
            { id: 2, from: "4081 7810 1234 5678", to: "external", amount: 3245.60, date: "2023-10-12", description: "Оплата за коммунальные услуги" },
            { id: 3, from: "external", to: "4081 7810 1234 5678", amount: 10000, date: "2023-10-10", description: "Пополнение счета" },
            { id: 4, from: "4081 7810 1234 5678", to: "deposit", amount: 50000, date: "2023-08-15", description: "Открытие вклада 'Солнечный Начинающий'" }
        ];
        
        // Навигация между разделами
        document.querySelectorAll('.nav-link').forEach(link => {
            link.addEventListener('click', function(e) {
                e.preventDefault();
                
                // Убираем активный класс у всех ссылок и разделов
                document.querySelectorAll('.nav-link').forEach(item => {
                    item.classList.remove('active');
                });
                document.querySelectorAll('.section').forEach(section => {
                    section.classList.remove('active');
                });
                
                // Добавляем активный класс к текущей ссылке и разделу
                this.classList.add('active');
                const targetId = this.getAttribute('href').substring(1);
                document.getElementById(targetId).classList.add('active');
                
                // Если переходим в историю, обновляем список транзакций
                if (targetId === 'history') {
                    updateTransactionHistory();
                }
                
                // Если переходим во вклады, обновляем список вкладов
                if (targetId === 'deposits') {
                    updateUserDeposits();
                }
            });
        });
        
        // Обработка выбора внешнего счета
        document.getElementById('toAccount').addEventListener('change', function() {
            const externalAccountGroup = document.getElementById('externalAccountGroup');
            if (this.value === 'other') {
                externalAccountGroup.style.display = 'block';
                document.getElementById('externalAccount').required = true;
            } else {
                externalAccountGroup.style.display = 'none';
                document.getElementById('externalAccount').required = false;
            }
        });
        
        // Кнопки перевода на карточках счетов
        document.querySelectorAll('.transfer-btn').forEach(btn => {
            btn.addEventListener('click', function() {
                const accountNumber = this.getAttribute('data-account');
                document.querySelector('.nav-link[href="#transfer"]').click();
                document.getElementById('fromAccount').value = accountNumber;
            });
        });
        
        // Быстрый перевод с главной страницы
        document.getElementById('quick-transfer').addEventListener('click', function() {
            document.querySelector('.nav-link[href="#transfer"]').click();
        });
        
        // Быстрое открытие вклада
        document.getElementById('quick-deposit').addEventListener('click', function() {
            document.querySelector('.nav-link[href="#deposits"]').click();
        });
        
        // Модальные окна
        const editNameModal = document.getElementById('editNameModal');
        const openDepositModal = document.getElementById('openDepositModal');
        
        // Закрытие модальных окон
        document.querySelectorAll('.close-modal').forEach(btn => {
            btn.addEventListener('click', function() {
                editNameModal.classList.remove('active');
                openDepositModal.classList.remove('active');
            });
        });
        
        document.getElementById('cancelEditName').addEventListener('click', function() {
            editNameModal.classList.remove('active');
        });
        
        document.getElementById('cancelDeposit').addEventListener('click', function() {
            openDepositModal.classList.remove('active');
        });
        
        // Изменение имени
        document.getElementById('editNameBtn').addEventListener('click', function() {
            document.getElementById('newFirstName').value = userData.firstName;
            document.getElementById('newLastName').value = userData.lastName;
            editNameModal.classList.add('active');
        });
        
        document.getElementById('saveName').addEventListener('click', function() {
            const newFirstName = document.getElementById('newFirstName').value;
            const newLastName = document.getElementById('newLastName').value;
            
            if (newFirstName && newLastName) {
                userData.firstName = newFirstName;
                userData.lastName = newLastName;
                
                // Обновляем отображение имени
                updateUserNameDisplay();
                
                // Закрываем модальное окно
                editNameModal.classList.remove('active');
                
                alert('Имя успешно изменено!');
            } else {
                alert('Пожалуйста, заполните все поля');
            }
        });
        
        // Открытие вклада
        document.querySelectorAll('.open-deposit-btn').forEach(btn => {
            btn.addEventListener('click', function() {
                const depositName = this.getAttribute('data-deposit');
                const depositRate = this.getAttribute('data-rate');
                
                document.getElementById('depositModalTitle').textContent = `Открытие вклада "${depositName}"`;
                
                // Заполняем детали вклада
                let depositDetails = '';
                if (depositName === 'Солнечный Начинающий') {
                    depositDetails = `
                        <p><strong>Ставка:</strong> ${depositRate}% годовых</p>
                        <p><strong>Срок:</strong> 6 месяцев</p>
                        <p><strong>Минимальная сумма:</strong> 10 000 ₽</p>
                    `;
                } else if (depositName === 'Солнечный Стандарт') {
                    depositDetails = `
                        <p><strong>Ставка:</strong> ${depositRate}% годовых</p>
                        <p><strong>Срок:</strong> 1 год</p>
                        <p><strong>Минимальная сумма:</strong> 50 000 ₽</p>
                    `;
                } else if (depositName === 'Солнечный Премиум') {
                    depositDetails = `
                        <p><strong>Ставка:</strong> ${depositRate}% годовых</p>
                        <p><strong>Срок:</strong> 2 года</p>
                        <p><strong>Минимальная сумма:</strong> 100 000 ₽</p>
                    `;
                }
                
                document.getElementById('depositDetails').innerHTML = depositDetails;
                
                // Сохраняем данные о вкладе для использования после подтверждения
                openDepositModal.setAttribute('data-deposit-name', depositName);
                openDepositModal.setAttribute('data-deposit-rate', depositRate);
                
                // Показываем модальное окно
                openDepositModal.classList.add('active');
            });
        });
        
        // Подтверждение открытия вклада
        document.getElementById('confirmDeposit').addEventListener('click', function() {
            const depositName = openDepositModal.getAttribute('data-deposit-name');
            const depositRate = parseFloat(openDepositModal.getAttribute('data-deposit-rate'));
            const depositAmount = parseFloat(document.getElementById('depositAmount').value);
            const sourceAccount = document.getElementById('depositSourceAccount').value;
            
            if (!depositAmount || depositAmount <= 0) {
                alert('Пожалуйста, введите корректную сумму вклада');
                return;
            }
            
            // Проверяем минимальную сумму в зависимости от типа вклада
            let minAmount = 0;
            if (depositName === 'Солнечный Начинающий') minAmount = 10000;
            else if (depositName === 'Солнечный Стандарт') minAmount = 50000;
            else if (depositName === 'Солнечный Премиум') minAmount = 100000;
            
            if (depositAmount < minAmount) {
                alert(`Минимальная сумма для вклада "${depositName}" составляет ${minAmount.toLocaleString('ru-RU')} ₽`);
                return;
            }
            
            // Проверяем достаточно ли средств на счете
            if (depositAmount > accounts[sourceAccount].balance) {
                alert('Недостаточно средств на выбранном счете');
                return;
            }
            
            // Определяем срок вклада в месяцах
            let termMonths = 0;
            if (depositName === 'Солнечный Начинающий') termMonths = 6;
            else if (depositName === 'Солнечный Стандарт') termMonths = 12;
            else if (depositName === 'Солнечный Премиум') termMonths = 24;
            
            // Создаем новый вклад
            const startDate = new Date();
            const endDate = new Date();
            endDate.setMonth(endDate.getMonth() + termMonths);
            
            const newDeposit = {
                id: deposits.length + 1,
                name: depositName,
                amount: depositAmount,
                rate: depositRate,
                term: termMonths,
                startDate: startDate.toISOString().split('T')[0],
                endDate: endDate.toISOString().split('T')[0]
            };
            
            deposits.push(newDeposit);
            
            // Списание средств со счета
            accounts[sourceAccount].balance -= depositAmount;
            
            // Добавляем транзакцию
            const newTransaction = {
                id: transactions.length + 1,
                from: sourceAccount,
                to: "deposit",
                amount: depositAmount,
                date: startDate.toISOString().split('T')[0],
                description: `Открытие вклада "${depositName}"`
            };
            
            transactions.unshift(newTransaction);
            
            // Обновляем отображение
            updateAccountBalances();
            updateUserDeposits();
            
            // Закрываем модальное окно
            openDepositModal.classList.remove('active');
            
            // Показываем уведомление об успехе
            alert(`Вклад "${depositName}" на сумму ${depositAmount.toLocaleString('ru-RU')} ₽ успешно открыт!`);
        });
        
        // Обработка формы перевода
        document.getElementById('transferForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            const fromAccount = document.getElementById('fromAccount').value;
            let toAccount = document.getElementById('toAccount').value;
            const amount = parseFloat(document.getElementById('amount').value);
            
            if (toAccount === 'other') {
                toAccount = document.getElementById('externalAccount').value;
                if (!toAccount) {
                    alert('Пожалуйста, укажите номер счета получателя');
                    return;
                }
            }
            
            if (fromAccount === toAccount) {
                alert('Нельзя переводить средства на тот же счет');
                return;
            }
            
            if (amount <= 0) {
                alert('Сумма перевода должна быть положительной');
                return;
            }
            
            if (amount > accounts[fromAccount].balance && accounts[fromAccount].balance >= 0) {
                alert('Недостаточно средств на счете');
                return;
            }
            
            // Выполняем перевод
            performTransfer(fromAccount, toAccount, amount);
            
            // Показываем уведомление об успехе
            alert(`Перевод на сумму ${amount.toLocaleString('ru-RU', {minimumFractionDigits: 2})} ₽ успешно выполнен!`);
            
            // Сбрасываем форму
            this.reset();
        });
        
        // Функция выполнения перевода
        function performTransfer(fromAccount, toAccount, amount) {
            // Обновляем балансы счетов
            if (fromAccount in accounts) {
                accounts[fromAccount].balance -= amount;
            }
            
            if (toAccount in accounts) {
                accounts[toAccount].balance += amount;
            }
            
            // Добавляем транзакцию в историю
            const newTransaction = {
                id: transactions.length + 1,
                from: fromAccount,
                to: toAccount,
                amount: amount,
                date: new Date().toISOString().split('T')[0],
                description: "Перевод между счетами"
            };
            
            transactions.unshift(newTransaction);
            
            // Обновляем отображение балансов на главной странице
            updateAccountBalances();
            
            // Обновляем историю операций, если она открыта
            if (document.getElementById('history').classList.contains('active')) {
                updateTransactionHistory();
            }
        }
        
        // Обновление отображения имени пользователя
        function updateUserNameDisplay() {
            const fullName = `${userData.firstName} ${userData.lastName}`;
            document.getElementById('userNameDisplay').textContent = fullName;
            document.getElementById('profileName').textContent = fullName;
            document.getElementById('welcomeMessage').textContent = `Добро пожаловать, ${userData.firstName}!`;
            document.getElementById('userAvatar').textContent = userData.firstName[0] + userData.lastName[0];
        }
        
        // Обновление отображения балансов счетов
        function updateAccountBalances() {
            for (const accountNumber in accounts) {
                const account = accounts[accountNumber];
                
                // Находим родительскую карточку счета и обновляем баланс
                const accountCards = document.querySelectorAll('.account-card');
                accountCards.forEach(card => {
                    if (card.querySelector('.account-number').textContent.includes(accountNumber)) {
                        const balanceElement = card.querySelector('.balance-amount');
                        balanceElement.textContent = `${account.balance.toLocaleString('ru-RU', {minimumFractionDigits: 2})} ${account.currency}`;
                        
                        // Обновляем цвет для кредитных карт
                        if (account.balance < 0) {
                            balanceElement.style.color = 'var(--danger-color)';
                        } else {
                            balanceElement.style.color = 'var(--dark-color)';
                        }
                    }
                });
                
                // Обновляем опции в формах
                const fromAccountSelect = document.getElementById('fromAccount');
                const toAccountSelect = document.getElementById('toAccount');
                const depositSourceSelect = document.getElementById('depositSourceAccount');
                
                [fromAccountSelect, toAccountSelect, depositSourceSelect].forEach(select => {
                    for (let i = 0; i < select.options.length; i++) {
                        const option = select.options[i];
                        if (option.value === accountNumber) {
                            option.text = `${accounts[accountNumber].type} (${account.balance.toLocaleString('ru-RU', {minimumFractionDigits: 2})} ${account.currency})`;
                        }
                    }
                });
            }
        }
        
        // Обновление списка вкладов пользователя
        function updateUserDeposits() {
            const userDepositsContainer = document.getElementById('userDeposits');
            userDepositsContainer.innerHTML = '';
            
            if (deposits.length === 0) {
                userDepositsContainer.innerHTML = `
                    <div style="grid-column: 1 / -1; text-align: center; padding: 40px; color: var(--gray-color);">
                        <i class="fas fa-piggy-bank" style="font-size: 3rem; margin-bottom: 15px;"></i>
                        <h3>У вас пока нет открытых вкладов</h3>
                        <p>Откройте первый вклад и начните получать дополнительный доход</p>
                    </div>
                `;
                return;
            }
            
            deposits.forEach(deposit => {
                const depositCard = document.createElement('div');
                depositCard.className = 'deposit-card';
                
                // Рассчитываем дату окончания и доход
                const startDate = new Date(deposit.startDate);
                const endDate = new Date(deposit.endDate);
                const now = new Date();
                const progress = Math.min(100, ((now - startDate) / (endDate - startDate)) * 100);
                const expectedIncome = (deposit.amount * deposit.rate * deposit.term / 12) / 100;
                
                depositCard.innerHTML = `
                    <div class="deposit-header">
                        <div class="deposit-name">${deposit.name}</div>
                        <div class="deposit-rate">${deposit.rate}%</div>
                    </div>
                    <div class="deposit-details">
                        <div class="deposit-detail">
                            <span>Сумма:</span>
                            <span>${deposit.amount.toLocaleString('ru-RU')} ₽</span>
                        </div>
                        <div class="deposit-detail">
                            <span>Срок:</span>
                            <span>${deposit.term} мес.</span>
                        </div>
                        <div class="deposit-detail">
                            <span>Дата открытия:</span>
                            <span>${formatDate(deposit.startDate)}</span>
                        </div>
                        <div class="deposit-detail">
                            <span>Дата окончания:</span>
                            <span>${formatDate(deposit.endDate)}</span>
                        </div>
                        <div class="deposit-detail">
                            <span>Ожидаемый доход:</span>
                            <span style="color: var(--success-color);">${expectedIncome.toLocaleString('ru-RU', {minimumFractionDigits: 2})} ₽</span>
                        </div>
                    </div>
                    <div style="margin-top: 15px;">
                        <div style="display: flex; justify-content: space-between; margin-bottom: 5px;">
                            <span>Прогресс:</span>
                            <span>${progress.toFixed(1)}%</span>
                        </div>
                        <div style="height: 8px; background: var(--primary-light); border-radius: 4px; overflow: hidden;">
                            <div style="height: 100%; width: ${progress}%; background: var(--primary-color);"></div>
                        </div>
                    </div>
                `;
                
                userDepositsContainer.appendChild(depositCard);
            });
        }
        
        // Обновление истории операций
        function updateTransactionHistory() {
            const transactionHistory = document.getElementById('transactionHistory');
            const accountFilter = document.getElementById('accountFilter').value;
            const typeFilter = document.getElementById('typeFilter').value;
            const periodFilter = document.getElementById('periodFilter').value;
            
            // Очищаем список
            transactionHistory.innerHTML = '';
            
            // Фильтруем транзакции
            let filteredTransactions = transactions.filter(transaction => {
                // Фильтр по счету
                if (accountFilter !== 'all') {
                    if (transaction.from !== accountFilter && transaction.to !== accountFilter) {
                        return false;
                    }
                }
                
                // Фильтр по типу операции
                if (typeFilter !== 'all') {
                    if (typeFilter === 'income' && !(transaction.to in accounts) && transaction.to !== 'deposit') {
                        return false;
                    }
                    if (typeFilter === 'outcome' && !(transaction.from in accounts)) {
                        return false;
                    }
                }
                
                // Фильтр по периоду
                if (periodFilter !== 'all') {
                    const transactionDate = new Date(transaction.date);
                    const now = new Date();
                    let daysDiff;
                    
                    if (periodFilter === 'month') {
                        daysDiff = 30;
                    } else if (periodFilter === 'week') {
                        daysDiff = 7;
                    }
                    
                    const timeDiff = now.getTime() - transactionDate.getTime();
                    const diffDays = Math.ceil(timeDiff / (1000 * 3600 * 24));
                    
                    if (diffDays > daysDiff) {
                        return false;
                    }
                }
                
                return true;
            });
            
            // Отображаем отфильтрованные транзакции
            filteredTransactions.forEach(transaction => {
                const li = document.createElement('li');
                li.className = 'transaction-item';
                
                const isIncome = (transaction.to in accounts) || transaction.to === 'deposit';
                const accountNumber = isIncome ? transaction.from : transaction.to;
                let accountType = '';
                
                if (accountNumber in accounts) {
                    accountType = accounts[accountNumber].type;
                } else if (accountNumber === 'deposit') {
                    accountType = 'Вклад';
                } else {
                    accountType = 'Внешний счет';
                }
                
                li.innerHTML = `
                    <div class="transaction-info">
                        <div class="transaction-name">${transaction.description}</div>
                        <div class="transaction-date">
                            <i class="far fa-calendar"></i> ${formatDate(transaction.date)}
                        </div>
                        <div style="font-size: 0.85rem; color: var(--gray-color);">
                            ${accountNumber} (${accountType})
                        </div>
                    </div>
                    <div class="transaction-amount ${isIncome ? 'positive' : 'negative'}">
                        ${isIncome ? '+' : '-'}${transaction.amount.toLocaleString('ru-RU', {minimumFractionDigits: 2})} ₽
                    </div>
                `;
                
                transactionHistory.appendChild(li);
            });
            
            // Если транзакций нет, показываем сообщение
            if (filteredTransactions.length === 0) {
                const li = document.createElement('li');
                li.className = 'transaction-item';
                li.style.textAlign = 'center';
                li.innerHTML = '<div class="transaction-info">Нет операций за выбранный период</div>';
                transactionHistory.appendChild(li);
            }
        }
        
        // Форматирование даты
        function formatDate(dateString) {
            const date = new Date(dateString);
            return date.toLocaleDateString('ru-RU');
        }
        
        // Обработчики фильтров истории
        document.getElementById('accountFilter').addEventListener('change', updateTransactionHistory);
        document.getElementById('typeFilter').addEventListener('change', updateTransactionHistory);
        document.getElementById('periodFilter').addEventListener('change', updateTransactionHistory);
        
        // Инициализация при загрузке страницы
        document.addEventListener('DOMContentLoaded', function() {
            updateUserNameDisplay();
            updateAccountBalances();
            updateUserDeposits();
            updateTransactionHistory();
        });
    </script>
</body>
</html>
