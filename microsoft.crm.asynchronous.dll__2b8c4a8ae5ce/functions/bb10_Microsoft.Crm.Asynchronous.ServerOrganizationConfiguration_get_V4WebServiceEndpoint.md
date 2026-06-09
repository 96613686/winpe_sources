# Microsoft.Crm.Asynchronous.ServerOrganizationConfiguration::get_V4WebServiceEndpoint

- ea: `0xbb10`
- end: `0xbb39`
- name: `Microsoft.Crm.Asynchronous.ServerOrganizationConfiguration::get_V4WebServiceEndpoint`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xbc50`

## string_xrefs

- `0xbb2d`: `2007/CrmService.asmx`

## pseudocode

```c

```

## disassembly

```asm
0xbb10  ldarg.0
0xbb11  call     instance string Microsoft.Crm.Asynchronous.ServerOrganizationConfiguration::GetSdkBaseUrl()
0xbb16  stloc.0
0xbb17  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbb1c  ldstr    a01_1// "{0}/{1}"
0xbb21  ldc.i4.2
0xbb22  newarr   [mscorlib]System.Object
0xbb27  dup
0xbb28  ldc.i4.0
0xbb29  ldloc.0
0xbb2a  stelem.ref
0xbb2b  dup
0xbb2c  ldc.i4.1
0xbb2d  ldstr    a2007Crmservice// "2007/CrmService.asmx"
0xbb32  stelem.ref
0xbb33  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xbb38  ret
```
