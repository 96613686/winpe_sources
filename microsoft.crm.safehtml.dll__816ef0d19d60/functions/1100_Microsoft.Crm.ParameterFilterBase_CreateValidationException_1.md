# Microsoft.Crm.ParameterFilterBase::CreateValidationException_1

- ea: `0x1100`
- end: `0x115d`
- name: `Microsoft.Crm.ParameterFilterBase::CreateValidationException_1`
- size: `93`
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
0x1100  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1105  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x110a  stloc.0
0x110b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1110  ldstr    aExpected0DataT// "Expected '{0}' data type for '{1}' para"...
0x1115  ldc.i4.6
0x1116  newarr   [mscorlib]System.Object
0x111b  dup
0x111c  ldc.i4.0
0x111d  ldarg.0
0x111e  stelem.ref
0x111f  dup
0x1120  ldc.i4.1
0x1121  ldarg.1
0x1122  stelem.ref
0x1123  dup
0x1124  ldc.i4.2
0x1125  ldarg.2
0x1126  call     string Microsoft.Crm.ParameterFilterBase::GetCollectionName(valuetype Microsoft.Crm.ParameterSources source)
0x112b  stelem.ref
0x112c  dup
0x112d  ldc.i4.3
0x112e  ldloc.0
0x112f  callvirt instance string [System.Web]System.Web.HttpRequest::get_HttpMethod()
0x1134  stelem.ref
0x1135  dup
0x1136  ldc.i4.4
0x1137  ldloc.0
0x1138  callvirt instance string [System.Web]System.Web.HttpRequest::get_RawUrl()
0x113d  stelem.ref
0x113e  dup
0x113f  ldc.i4.5
0x1140  ldloc.0
0x1141  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Headers()
0x1146  ldstr    aReferer// "Referer"
0x114b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1150  stelem.ref
0x1151  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1156  ldarg.3
0x1157  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string, class [mscorlib]System.Exception)
0x115c  ret
```
