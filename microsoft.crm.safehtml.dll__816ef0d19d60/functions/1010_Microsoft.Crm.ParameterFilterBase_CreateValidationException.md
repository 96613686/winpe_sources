# Microsoft.Crm.ParameterFilterBase::CreateValidationException

- ea: `0x1010`
- end: `0x106c`
- name: `Microsoft.Crm.ParameterFilterBase::CreateValidationException`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1290`

## callees

- `0x1320`

## pseudocode

```c

```

## disassembly

```asm
0x1010  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1015  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x101a  stloc.0
0x101b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1020  ldstr    aExpected0DataT// "Expected '{0}' data type for '{1}' para"...
0x1025  ldc.i4.6
0x1026  newarr   [mscorlib]System.Object
0x102b  dup
0x102c  ldc.i4.0
0x102d  ldarg.0
0x102e  stelem.ref
0x102f  dup
0x1030  ldc.i4.1
0x1031  ldarg.1
0x1032  stelem.ref
0x1033  dup
0x1034  ldc.i4.2
0x1035  ldarg.2
0x1036  call     string Microsoft.Crm.ParameterFilterBase::GetCollectionName(valuetype Microsoft.Crm.ParameterSources source)
0x103b  stelem.ref
0x103c  dup
0x103d  ldc.i4.3
0x103e  ldloc.0
0x103f  callvirt instance string [System.Web]System.Web.HttpRequest::get_HttpMethod()
0x1044  stelem.ref
0x1045  dup
0x1046  ldc.i4.4
0x1047  ldloc.0
0x1048  callvirt instance string [System.Web]System.Web.HttpRequest::get_RawUrl()
0x104d  stelem.ref
0x104e  dup
0x104f  ldc.i4.5
0x1050  ldloc.0
0x1051  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Headers()
0x1056  ldstr    aReferer// "Referer"
0x105b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1060  stelem.ref
0x1061  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1066  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x106b  ret
```
