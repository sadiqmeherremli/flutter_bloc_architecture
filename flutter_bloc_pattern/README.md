# f FLutter Bloc || Clean Arhictecture

Project Structure



lib/
├── core/
│   ├── error/
│   ├── usecases/
│   ├── utils/
│   └── widgets/
├── features/
│   ├── feature_name/
│   │   ├── data/
│   │   │   ├── data_sources/
│   │   │   ├── models/
│   │   │   └── repositories/
│   │   ├── domain/
│   │   │   ├── entities/
│   │   │   ├── repositories/
│   │   │   └── usecases/
│   │   └── presentation/
│   │       ├── bloc/
│   │       ├── pages/
│   │       └── widgets/
├── config/
│   ├── routes.dart
│   └── themes.dart
└── main.dart

Folder Explanations

1. Core

This folder contains reusable components, utilities, and shared logic used throughout the app.
	•	error/
Handles global error management, such as custom exceptions or failure classes.
Example: ServerException, Failure.
	•	usecases/
Shared use cases that don’t belong to a specific feature. These are application-agnostic operations.
	•	utils/
Utility functions or constants that are reusable across the app.
Example: Formatters, Validators.
	•	widgets/
Common UI components shared across multiple features.
Example: Custom buttons, loaders, or dialogs.

2. Features

Each feature of your app gets its own folder.
For example, in an e-commerce app, features might include: products, auth, cart, orders.

Inside a Feature

Each feature folder is broken down into three layers:
	1.	Data Layer
	•	Responsible for handling raw data from external sources (e.g., API, database).
	•	Subfolders:
	•	data_sources/: Contains classes to fetch data (e.g., API calls or database queries).
	•	models/: Data models used for parsing and serializing raw data.
	•	repositories/: Implements domain repositories using data sources.
Example:

features/products/data/
├── data_sources/
│   ├── product_remote_data_source.dart
│   └── product_local_data_source.dart
├── models/
│   └── product_model.dart
└── repositories/
    └── product_repository_impl.dart


	2.	Domain Layer
	•	Contains the business logic of the app.
	•	Subfolders:
	•	entities/: Core models that represent the data in its simplest form (e.g., Product).
	•	repositories/: Abstract definitions of repositories.
	•	usecases/: Contains specific business operations (e.g., GetProducts).
Example:

features/products/domain/
├── entities/
│   └── product.dart
├── repositories/
│   └── product_repository.dart
└── usecases/
    └── get_products.dart


	3.	Presentation Layer
	•	Contains everything related to the UI.
	•	Subfolders:
	•	bloc/: Handles state management (e.g., ProductBloc).
	•	pages/: Screens and pages related to the feature (e.g., ProductListPage).
	•	widgets/: Feature-specific reusable widgets.
Example:

features/products/presentation/
├── bloc/
│   ├── product_bloc.dart
│   ├── product_event.dart
│   └── product_state.dart
├── pages/
│   └── product_list_page.dart
└── widgets/
    └── product_tile.dart

3. Config

This folder contains app-wide configurations.
	•	routes.dart:
Manages navigation routes for the entire app.
	•	themes.dart:
Contains global theme data like colors, typography, and light/dark mode styles.

4. Main File
	•	main.dart:
The entry point of the app. Initializes dependencies and starts the app.

Example: E-commerce App Structure

lib/
├── core/
│   ├── error/
│   ├── usecases/
│   ├── utils/
│   └── widgets/
├── features/
│   ├── auth/
│   │   ├── data/
│   │   ├── domain/
│   │   └── presentation/
│   ├── products/
│   │   ├── data/
│   │   ├── domain/
│   │   └── presentation/
│   ├── cart/
│   │   ├── data/
│   │   ├── domain/
│   │   └── presentation/
│   └── orders/
│       ├── data/
│       ├── domain/
│       └── presentation/
├── config/
│   ├── routes.dart
│   └── themes.dart
└── main.dart










----------------------------------------------------








Qovluqların İzahı

1. Core (Ümumi resurslar)

Bu qovluq tətbiq boyu istifadə olunan ümumi komponentlər, util funksiyalar və paylaşılmış məntiqi ehtiva edir.
	•	error/
Tətbiqdə baş verə biləcək səhvləri idarə etmək üçün istifadə olunur (məsələn, xüsusi istisnalar və ya uğursuzluqlar).
Nümunə: ServerException, Failure.
	•	usecases/
Konkret bir xüsusiyyətə aid olmayan, tətbiqdə ümumi istifadə edilən məntiqi əməliyyatlar burada saxlanılır.
	•	utils/
Tətbiqdə təkrarlanan util funksiyalar və ya konstantlar burada yerləşir.
Nümunə: Tarix formatlama funksiyaları, validatorlar.
	•	widgets/
Bir neçə xüsusiyyətdə istifadə oluna bilən ümumi UI komponentləri.
Nümunə: Xüsusi düymələr, yükləmə indikatorları və s.

2. Features (Xüsusiyyətlər)

Hər bir xüsusiyyət üçün ayrıca bir qovluq yaradılır.
Məsələn, e-ticarət tətbiqi üçün xüsusiyyətlər bunlar ola bilər: products, auth, cart, orders.

Bir Xüsusiyyət Qovluğu

Hər bir xüsusiyyət aşağıdakı 3 əsas təbəqəyə bölünür:
	1.	Data Layer (Məlumat təbəqəsi)
	•	Xarici mənbələrdən (API, lokal verilənlər bazası və s.) məlumatları alır və işləyir.
	•	Alt qovluqlar:
	•	data_sources/: Məlumat mənbələrindən (API, verilənlər bazası) məlumatı əldə edən siniflər.
	•	models/: Gələn məlumatları emal etmək üçün istifadə olunan data modelləri.
	•	repositories/: Domain səviyyəsində istifadə olunan repositories-in implementasiyası.
Nümunə:

features/products/data/
├── data_sources/
│   ├── product_remote_data_source.dart
│   └── product_local_data_source.dart
├── models/
│   └── product_model.dart
└── repositories/
    └── product_repository_impl.dart


	2.	Domain Layer (Domen Təbəqəsi)
	•	Tətbiqin iş məntiqini özündə saxlayır.
	•	Alt qovluqlar:
	•	entities/: Əsas məlumat modelləri. Təmiz və sadə strukturlardır.
	•	repositories/: Repositories üçün abstrakt interfeyslər.
	•	usecases/: Konkret iş məntiqi əməliyyatlarını ehtiva edir (məsələn, GetProducts).
Nümunə:

features/products/domain/
├── entities/
│   └── product.dart
├── repositories/
│   └── product_repository.dart
└── usecases/
    └── get_products.dart


	3.	Presentation Layer (Təqdimat Təbəqəsi)
	•	UI və istifadəçi qarşılıqlı əlaqəsini idarə edir.
	•	Alt qovluqlar:
	•	bloc/: BLoC və ya Cubit sinifləri. UI-nin vəziyyətini idarə edir.
	•	pages/: Xüsusiyyətə aid ekranlar və səhifələr.
	•	widgets/: Xüsusiyyətə aid reusable widgetlər.
Nümunə:

features/products/presentation/
├── bloc/
│   ├── product_bloc.dart
│   ├── product_event.dart
│   └── product_state.dart
├── pages/
│   └── product_list_page.dart
└── widgets/
    └── product_tile.dart

3. Config (Tənzimləmə)

Bu qovluq tətbiqin qlobal tənzimləmələrini saxlayır.
	•	routes.dart:
Tətbiqin naviqasiya yollarını idarə edir.
	•	themes.dart:
Rənglər, şriftlər və ümumi mövzu konfiqurasiyaları burada saxlanılır.

4. Main File
	•	main.dart:
Tətbiqin başlanğıc nöqtəsi. Bütün asılılıqlar buradan başlatılır.

E-Ticarət Tətbiqi Üçün Nümunə Strukturu

lib/
├── core/
│   ├── error/
│   ├── usecases/
│   ├── utils/
│   └── widgets/
├── features/
│   ├── auth/
│   │   ├── data/
│   │   ├── domain/
│   │   └── presentation/
│   ├── products/
│   │   ├── data/
│   │   ├── domain/
│   │   └── presentation/
│   ├── cart/
│   │   ├── data/
│   │   ├── domain/
│   │   └── presentation/
│   └── orders/
│       ├── data/
│       ├── domain/
│       └── presentation/
├── config/
│   ├── routes.dart
│   └── themes.dart
└── main.dart