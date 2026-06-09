# Microsoft.Crm.Authentication.ActiveDirectoryUserInformation::GetUserToken

- ea: `0x5c70`
- end: `0x5c9d`
- name: `Microsoft.Crm.Authentication.ActiveDirectoryUserInformation::GetUserToken`
- size: `45`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x5c30`
- `0x5d30`
- `0x5dd0`

## pseudocode

```c

```

## disassembly

```asm
0x5c70  ldarg.0
0x5c71  ldstr    aSid// "sid"
0x5c76  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x5c7b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5c80  ldstr    a01_0// "{0}:{1}"
0x5c85  ldc.i4.2
0x5c86  newarr   [mscorlib]System.Object
0x5c8b  dup
0x5c8c  ldc.i4.0
0x5c8d  ldstr    aW// "W"
0x5c92  stelem.ref
0x5c93  dup
0x5c94  ldc.i4.1
0x5c95  ldarg.0
0x5c96  stelem.ref
0x5c97  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5c9c  ret
```
