# Microsoft.Crm.ParameterFilterBase::CreateValidationException_0

- ea: `0x1070`
- end: `0x10f7`
- name: `Microsoft.Crm.ParameterFilterBase::CreateValidationException_0`
- size: `135`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1300`
- `0x1370`

## callees

- `0x1070`
- `0x1320`

## pseudocode

```c

```

## disassembly

```asm
0x1070  ldarg.1
0x1071  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1076  brtrue.s loc_1097
0x1078  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x107d  ldstr    a01// "{0}={1}"
0x1082  ldc.i4.2
0x1083  newarr   [mscorlib]System.Object
0x1088  dup
0x1089  ldc.i4.0
0x108a  ldarg.1
0x108b  stelem.ref
0x108c  dup
0x108d  ldc.i4.1
0x108e  ldarg.2
0x108f  stelem.ref
0x1090  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1095  br.s     loc_1098
0x1097  ldarg.2
0x1098  stloc.0
0x1099  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x109e  ldstr    aCrmParameterFi// "CRM Parameter Filter - Invalid paramete"...
0x10a3  ldc.i4.7
0x10a4  newarr   [mscorlib]System.Object
0x10a9  dup
0x10aa  ldc.i4.0
0x10ab  ldloc.0
0x10ac  stelem.ref
0x10ad  dup
0x10ae  ldc.i4.1
0x10af  ldarg.3
0x10b0  call     string Microsoft.Crm.ParameterFilterBase::GetCollectionName(valuetype Microsoft.Crm.ParameterSources source)
0x10b5  stelem.ref
0x10b6  dup
0x10b7  ldc.i4.2
0x10b8  ldarg.0
0x10b9  callvirt instance string [System.Web]System.Web.HttpRequest::get_FilePath()
0x10be  stelem.ref
0x10bf  dup
0x10c0  ldc.i4.3
0x10c1  call     string [mscorlib]System.Environment::get_NewLine()
0x10c6  stelem.ref
0x10c7  dup
0x10c8  ldc.i4.4
0x10c9  ldarg.0
0x10ca  callvirt instance string [System.Web]System.Web.HttpRequest::get_HttpMethod()
0x10cf  stelem.ref
0x10d0  dup
0x10d1  ldc.i4.5
0x10d2  ldarg.0
0x10d3  callvirt instance string [System.Web]System.Web.HttpRequest::get_RawUrl()
0x10d8  stelem.ref
0x10d9  dup
0x10da  ldc.i4.6
0x10db  ldarg.0
0x10dc  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Headers()
0x10e1  ldstr    aReferer// "Referer"
0x10e6  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x10eb  stelem.ref
0x10ec  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x10f1  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x10f6  ret
```
