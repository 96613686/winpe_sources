# Microsoft.Crm.Asynchronous.ServerOrganizationConfiguration::get_MetadataWebServiceEndpoint

- ea: `0xbb40`
- end: `0xbb69`
- name: `Microsoft.Crm.Asynchronous.ServerOrganizationConfiguration::get_MetadataWebServiceEndpoint`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xbc50`

## string_xrefs

- `0xbb5d`: `2007/MetadataService.asmx`

## pseudocode

```c

```

## disassembly

```asm
0xbb40  ldarg.0
0xbb41  call     instance string Microsoft.Crm.Asynchronous.ServerOrganizationConfiguration::GetSdkBaseUrl()
0xbb46  stloc.0
0xbb47  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbb4c  ldstr    a01_1// "{0}/{1}"
0xbb51  ldc.i4.2
0xbb52  newarr   [mscorlib]System.Object
0xbb57  dup
0xbb58  ldc.i4.0
0xbb59  ldloc.0
0xbb5a  stelem.ref
0xbb5b  dup
0xbb5c  ldc.i4.1
0xbb5d  ldstr    a2007Metadatase// "2007/MetadataService.asmx"
0xbb62  stelem.ref
0xbb63  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xbb68  ret
```
