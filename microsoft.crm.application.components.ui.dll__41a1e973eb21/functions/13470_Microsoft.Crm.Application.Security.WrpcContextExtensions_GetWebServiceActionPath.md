# Microsoft.Crm.Application.Security.WrpcContextExtensions::GetWebServiceActionPath

- ea: `0x13470`
- end: `0x1348f`
- name: `Microsoft.Crm.Application.Security.WrpcContextExtensions::GetWebServiceActionPath`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x4c60`

## string_xrefs

- `0x13475`: `/AppWebServices/{0}.asmx`

## pseudocode

```c

```

## disassembly

```asm
0x13470  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13475  ldstr    aAppwebservices_0// "/AppWebServices/{0}.asmx"
0x1347a  ldc.i4.1
0x1347b  newarr   [mscorlib]System.Object
0x13480  dup
0x13481  ldc.i4.0
0x13482  ldarg.0
0x13483  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlEncode(string)
0x13488  stelem.ref
0x13489  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1348e  ret
```
