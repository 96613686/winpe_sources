# Microsoft.Crm.Authentication.FederatedUserInformation::GetUserToken

- ea: `0x5f30`
- end: `0x5f6d`
- name: `Microsoft.Crm.Authentication.FederatedUserInformation::GetUserToken`
- size: `61`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x7f0`
- `0x5ec0`
- `0xca00`
- `0xcd40`
- `0xea80`
- `0xef20`

## callees

- `0x5f30`

## pseudocode

```c

```

## disassembly

```asm
0x5f30  ldarg.0
0x5f31  ldstr    aUserprincipaln// "userPrincipalName"
0x5f36  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x5f3b  ldarg.0
0x5f3c  ldstr    aC// "C:"
0x5f41  ldc.i4.4
0x5f42  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x5f47  brfalse.s loc_5F6B
0x5f49  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5f4e  ldstr    a01_0// "{0}:{1}"
0x5f53  ldc.i4.2
0x5f54  newarr   [mscorlib]System.Object
0x5f59  dup
0x5f5a  ldc.i4.0
0x5f5b  ldstr    aC_0// "C"
0x5f60  stelem.ref
0x5f61  dup
0x5f62  ldc.i4.1
0x5f63  ldarg.0
0x5f64  stelem.ref
0x5f65  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5f6a  ret
0x5f6b  ldarg.0
0x5f6c  ret
```
