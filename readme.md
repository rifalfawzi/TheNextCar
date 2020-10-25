# Next Car
- sebuah project Next Car untuk membuat perjalanan lebih aman

# Fungsi
-  Membuat perjalanan mobil lebih aman
- Bisa menyalakan dan mematikan Accu
- Membuat kenyamanan
# Cara Kerja
Tidak bisa menyalakan mesin jika pintu mobil belum terkunci dengan sempurna, jika tidak di switch on maka mobil tidak akan bisa menyala.

Diawali dengan "MainWindows" pada class "MainWindows.xaml.cs" kita mendeklarasikan sebuah fungsi calculator

```csharp
  ‌‌public‌‌ ‌‌partial‌‌ ‌‌class‌‌ ‌‌MainWindow‌‌ ‌:‌ ‌‌Window‌ ‌
    ‌{‌ ‌
        ‌‌public‌‌ ‌‌MainWindow‌()‌ ‌
        ‌{‌ ‌
            ‌InitializeComponent()‌ ‌
        ‌}‌ ‌
 ‌
 ‌
        ‌‌private‌‌ ‌‌void‌‌ ‌‌OnAccuButtonClicked‌(‌object‌‌ ‌sender,‌ ‌RoutedEventArgs‌ ‌e)‌ ‌
        ‌{‌ ‌
            ‌Console.WriteLine(‌"button‌ ‌aki"‌)‌ ‌
        ‌}‌ ‌
 ‌
        ‌‌private‌‌ ‌‌void‌‌ ‌‌OnDoorOpenButtonClicked‌(‌object‌‌ ‌sender,‌ ‌ ‌
                ‌RoutedEventArgs‌ ‌e)‌ ‌
        ‌{‌ ‌
            ‌Console.WriteLine(‌"button‌ ‌pintu"‌)‌ ‌
        ‌}‌ ‌
        ‌private‌‌ ‌‌void‌‌ ‌‌OnLockDoorButtonClicked‌(‌object‌‌ ‌sender,‌ ‌ ‌
                ‌RoutedEventArgs‌ ‌e)‌ ‌
        ‌{‌ ‌
            ‌Console.WriteLine(‌"button‌ ‌kunci‌ ‌pintu"‌)‌ ‌
        ‌}‌ ‌
 ‌
        ‌‌private‌‌ ‌‌void‌‌ ‌‌OnStartButtonClicked‌(‌object‌‌ ‌sender,‌ ‌RoutedEventArgs‌ ‌e)‌ ‌
        ‌{‌ ‌
            ‌Console.WriteLine(‌"button‌ ‌start"‌)‌ ‌

```

kemudian pada car.cs

```csharp
 ‌‌public‌‌ ‌‌void‌‌ ‌‌toggleStartEngineButton‌()‌ ‌
        ‌{‌ ‌
            ‌‌if‌‌ ‌(!doorIsClosed())‌ ‌
            ‌{‌ ‌
                ‌‌this‌.callbackCarEngineStatusChanged.carEngineStatusChanged(‌"STOPPED"‌,‌ ‌‌"door‌ ‌is‌ ‌open"‌);‌ ‌
                ‌‌return‌;‌ ‌
            ‌}‌ ‌
            ‌‌if‌‌ ‌(!doorIsLocked())‌ ‌
            ‌{‌ ‌
                ‌‌this‌.callbackCarEngineStatusChanged.carEngineStatusChanged(‌"STOPPED"‌,‌ ‌‌"door‌ ‌unlocked"‌);‌ ‌
                ‌‌return‌;‌ ‌
            ‌}‌ ‌
            ‌‌if‌‌ ‌(!powerIsReady())‌ ‌
            ‌{‌ ‌
                ‌‌this‌.callbackCarEngineStatusChanged.carEngineStatusChanged(‌"STOPPED"‌,‌ ‌ ‌
                         ‌‌"no‌ ‌power‌ ‌available"‌);‌ ‌
                ‌‌return‌;‌ ‌
            ‌}‌ ‌
            ‌‌this‌.callbackCarEngineStatusChanged.carEngineStatusChanged(‌"STARTED"‌,‌ ‌‌"Engine‌ ‌started"‌);‌ ‌
        ‌}‌ 
```
