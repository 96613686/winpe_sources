# Microsoft.Crm.Extensibility.OrganizationDataServiceQueryProvider::System.Data.Services.Providers.IDataServiceQueryProvider.GetOpenPropertyValue

- ea: `0x7c70`
- end: `0x7c9f`
- name: `Microsoft.Crm.Extensibility.OrganizationDataServiceQueryProvider::System.Data.Services.Providers.IDataServiceQueryProvider.GetOpenPropertyValue`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x7c76`: `Requesting open property value {0} on type {1}`

## pseudocode

```c

```

## disassembly

```asm
0x7c70  ldc.i4.0
0x7c71  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7c76  ldstr    aRequestingOpen// "Requesting open property value {0} on t"...
0x7c7b  ldc.i4.2
0x7c7c  newarr   [mscorlib]System.Object
0x7c81  dup
0x7c82  ldc.i4.0
0x7c83  ldarg.2
0x7c84  stelem.ref
0x7c85  dup
0x7c86  ldc.i4.1
0x7c87  ldarg.1
0x7c88  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x7c8d  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x7c92  stelem.ref
0x7c93  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7c98  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x7c9d  ldnull
0x7c9e  ret
```
