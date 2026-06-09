# Microsoft.Crm.ParameterFilterBase::ValidateParametersInternal

- ea: `0x1370`
- end: `0x1463`
- name: `Microsoft.Crm.ParameterFilterBase::ValidateParametersInternal`
- size: `243`
- prototype: ``
- caller_count: `5`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0xea0`
- `0xee0`
- `0xf20`
- `0xf70`
- `0xfa0`

## callees

- `0x350`
- `0x360`
- `0x370`
- `0x1070`
- `0x1160`
- `0x1180`
- `0x11d0`
- `0x1300`
- `0x1370`

## pseudocode

```c

```

## disassembly

```asm
0x1370  ldarg.0
0x1371  ldarg.1
0x1372  call     instance bool Microsoft.Crm.ParameterFilterBase::ShouldValidateParameters(object resource)
0x1377  brtrue.s loc_137A
0x1379  ret
0x137a  ldarg.2
0x137b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1380  callvirt instance class [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection [System]System.Collections.Specialized.NameObjectCollectionBase::get_Keys()
0x1385  callvirt instance class [mscorlib]System.Collections.IEnumerator [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection::GetEnumerator()
0x138a  stloc.0
0x138b  br.s     loc_13B6
0x138d  ldloc.0
0x138e  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1393  castclass [mscorlib]System.String
0x1398  stloc.1
0x1399  ldarg.2
0x139a  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x139f  ldloc.1
0x13a0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x13a5  stloc.2
0x13a6  ldarg.0
0x13a7  ldarg.2
0x13a8  ldarg.3
0x13a9  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.Crm.PageParameters::get_QueryStringParameters()
0x13ae  ldloc.1
0x13af  ldloc.2
0x13b0  ldc.i4.1
0x13b1  call     instance void Microsoft.Crm.ParameterFilterBase::ValidateParameter(class [System.Web]System.Web.HttpRequest request, class [mscorlib]System.Collections.ArrayList parameterCollection, string key, string value, valuetype Microsoft.Crm.ParameterSources source)
0x13b6  ldloc.0
0x13b7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x13bc  brtrue.s loc_138D
0x13be  leave.s  loc_13D1
0x13c0  ldloc.0
0x13c1  isinst   [mscorlib]System.IDisposable
0x13c6  stloc.3
0x13c7  ldloc.3
0x13c8  brfalse.s loc_13D0
0x13ca  ldloc.3
0x13cb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13d0  endfinally
0x13d1  ldarg.2
0x13d2  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x13d7  callvirt instance class [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection [System]System.Collections.Specialized.NameObjectCollectionBase::get_Keys()
0x13dc  callvirt instance class [mscorlib]System.Collections.IEnumerator [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection::GetEnumerator()
0x13e1  stloc.0
0x13e2  br.s     loc_1412
0x13e4  ldloc.0
0x13e5  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x13ea  castclass [mscorlib]System.String
0x13ef  stloc.s  4
0x13f1  ldarg.2
0x13f2  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x13f7  ldloc.s  4
0x13f9  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x13fe  stloc.s  5
0x1400  ldarg.0
0x1401  ldarg.2
0x1402  ldarg.3
0x1403  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.Crm.PageParameters::get_FormParameters()
0x1408  ldloc.s  4
0x140a  ldloc.s  5
0x140c  ldc.i4.2
0x140d  call     instance void Microsoft.Crm.ParameterFilterBase::ValidateParameter(class [System.Web]System.Web.HttpRequest request, class [mscorlib]System.Collections.ArrayList parameterCollection, string key, string value, valuetype Microsoft.Crm.ParameterSources source)
0x1412  ldloc.0
0x1413  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1418  brtrue.s loc_13E4
0x141a  leave.s  loc_142D
0x141c  ldloc.0
0x141d  isinst   [mscorlib]System.IDisposable
0x1422  stloc.3
0x1423  ldloc.3
0x1424  brfalse.s loc_142C
0x1426  ldloc.3
0x1427  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x142c  endfinally
0x142d  ldarg.2
0x142e  call     bool Microsoft.Crm.ParameterFilterBase::HasFormStream(class [System.Web]System.Web.HttpRequest request)
0x1433  brfalse.s loc_1462
0x1435  ldarg.2
0x1436  call     string Microsoft.Crm.ParameterFilterBase::GetInputStream(class [System.Web]System.Web.HttpRequest request)
0x143b  stloc.s  6
0x143d  ldarg.3
0x143e  callvirt instance bool Microsoft.Crm.PageParameters::get_ExpectsFormStream()
0x1443  brfalse.s loc_1457
0x1445  ldarg.0
0x1446  ldarg.2
0x1447  ldarg.3
0x1448  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.Crm.PageParameters::get_FormParameters()
0x144d  ldnull
0x144e  ldloc.s  6
0x1450  ldc.i4.4
0x1451  call     instance void Microsoft.Crm.ParameterFilterBase::ValidateParameter(class [System.Web]System.Web.HttpRequest request, class [mscorlib]System.Collections.ArrayList parameterCollection, string key, string value, valuetype Microsoft.Crm.ParameterSources source)
0x1456  ret
0x1457  ldarg.2
0x1458  ldnull
0x1459  ldloc.s  6
0x145b  ldc.i4.4
0x145c  call     class [mscorlib]System.Exception Microsoft.Crm.ParameterFilterBase::CreateValidationException(class [System.Web]System.Web.HttpRequest request, string key, string value, valuetype Microsoft.Crm.ParameterSources source)
0x1461  throw
0x1462  ret
```
