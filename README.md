# cs-tuple

## namespace form_02

### 定数の補完文字列
```cs
    const string Language = "C#";
    const string Platform = ".NET";
    const string Version = "10.0";

    // 定数の補間文字列( C# 10 )
    const string FullProductName = $"{Platform} - Language: {Language} Version: {Version}";

    const string D = "DBG";
```

### タプル
```cs
    private void action_Click(object sender, EventArgs e)
    {
        Debug.WriteLine($"{D}:{FullProductName}");

        var tuple = TupleAction();

        Debug.WriteLine($"{D}:{tuple.a} , {tuple.b}");

        Person person = new Person();

        if ( person.FirstName != null ) {
            Debug.WriteLine($"{D}:NULL ではない");
        }
        if ( person.LastName == null ) {
            Debug.WriteLine($"{D}:NULL である");
        }

    }

    // タプルの戻り値を返すメソッド
    private (double a, int b) TupleAction()
    {
        var t = (Sum: 4.5, Count: 3);
        Debug.WriteLine($"{D}:Sum of {t.Count} elements is {t.Sum}.");

        (double Sum, int Count) d = (4.5, 3);
        Debug.WriteLine($"{D}:Sum of {d.Count} elements is {d.Sum}.");

        var x = (4.5, 3);
        Debug.WriteLine($"{D}:Sum of {x.Item2} elements is {x.Item1}.");

        return( x.Item1, x.Item2 );
    }
```
