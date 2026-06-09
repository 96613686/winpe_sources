# Microsoft.Crm.SdkTypeProxy.CrmTypes::CreateCrmDateTimeFromUser

- ea: `0x377b0`
- end: `0x377d6`
- name: `Microsoft.Crm.SdkTypeProxy.CrmTypes::CreateCrmDateTimeFromUser`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x37480`

## pseudocode

```c

```

## disassembly

```asm
0x377b0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x377b5  ldstr    a0S// "{0:s}"
0x377ba  ldc.i4.1
0x377bb  newarr   [mscorlib]System.Object
0x377c0  stloc.0
0x377c1  ldloc.0
0x377c2  ldc.i4.0
0x377c3  ldarg.0
0x377c4  box      [mscorlib]System.DateTime
0x377c9  stelem.ref
0x377ca  ldloc.0
0x377cb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x377d0  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime Microsoft.Crm.SdkTypeProxy.CrmTypes::CreateCrmDateTime(string value)
0x377d5  ret
```
