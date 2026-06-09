# Microsoft.Crm.Extensibility.OrganizationDataServiceQueryProvider::System.Data.Services.Providers.IDataServiceQueryProvider.GetOpenPropertyValues

- ea: `0x7ca0`
- end: `0x7ccb`
- name: `Microsoft.Crm.Extensibility.OrganizationDataServiceQueryProvider::System.Data.Services.Providers.IDataServiceQueryProvider.GetOpenPropertyValues`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x7ca6`: `Requesting open property values on type {0} `

## pseudocode

```c

```

## disassembly

```asm
0x7ca0  ldc.i4.0
0x7ca1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7ca6  ldstr    aRequestingOpen_0// "Requesting open property values on type"...
0x7cab  ldc.i4.1
0x7cac  newarr   [mscorlib]System.Object
0x7cb1  dup
0x7cb2  ldc.i4.0
0x7cb3  ldarg.1
0x7cb4  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x7cb9  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x7cbe  stelem.ref
0x7cbf  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7cc4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x7cc9  ldnull
0x7cca  ret
```
