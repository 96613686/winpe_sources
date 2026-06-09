# Microsoft.Crm.Authentication.PassportUserInformation::GetUserToken

- ea: `0x62e0`
- end: `0x631d`
- name: `Microsoft.Crm.Authentication.PassportUserInformation::GetUserToken`
- size: `61`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x7f0`
- `0x62a0`
- `0x6360`
- `0x6410`

## callees

- `0x62e0`

## pseudocode

```c

```

## disassembly

```asm
0x62e0  ldarg.0
0x62e1  ldstr    aUserprincipaln// "userPrincipalName"
0x62e6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x62eb  ldarg.0
0x62ec  ldstr    aP// "P:"
0x62f1  ldc.i4.4
0x62f2  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x62f7  brfalse.s loc_631B
0x62f9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x62fe  ldstr    a01_0// "{0}:{1}"
0x6303  ldc.i4.2
0x6304  newarr   [mscorlib]System.Object
0x6309  dup
0x630a  ldc.i4.0
0x630b  ldstr    aP_0// "P"
0x6310  stelem.ref
0x6311  dup
0x6312  ldc.i4.1
0x6313  ldarg.0
0x6314  stelem.ref
0x6315  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x631a  ret
0x631b  ldarg.0
0x631c  ret
```
