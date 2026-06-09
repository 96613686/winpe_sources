# Microsoft.Crm.SdkTypeProxy.CrmTypes::CreateCrmDateTimeFromUniversal

- ea: `0x377e0`
- end: `0x37806`
- name: `Microsoft.Crm.SdkTypeProxy.CrmTypes::CreateCrmDateTimeFromUniversal`
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
0x377e0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x377e5  ldstr    a0SZ// "{0:s}Z"
0x377ea  ldc.i4.1
0x377eb  newarr   [mscorlib]System.Object
0x377f0  stloc.0
0x377f1  ldloc.0
0x377f2  ldc.i4.0
0x377f3  ldarg.0
0x377f4  box      [mscorlib]System.DateTime
0x377f9  stelem.ref
0x377fa  ldloc.0
0x377fb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x37800  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime Microsoft.Crm.SdkTypeProxy.CrmTypes::CreateCrmDateTime(string value)
0x37805  ret
```
