# Microsoft.Crm.Sdk.InProcessCrmService::ConvertToDynamicRequest

- ea: `0x3200`
- end: `0x3308`
- name: `Microsoft.Crm.Sdk.InProcessCrmService::ConvertToDynamicRequest`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x2e20`

## callees

- `0x1380`
- `0x3200`
- `0x45e0`
- `0x45f0`
- `0x4ad0`
- `0x5d30`
- `0x5d40`
- `0x5d60`
- `0xa9c0`

## pseudocode

```c

```

## disassembly

```asm
0x3200  ldarg.1
0x3201  ldstr    aStrongtypedreq// "strongTypedRequest"
0x3206  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x320b  ldarg.1
0x320c  isinst   Microsoft.Crm.Sdk.RequestBase
0x3211  stloc.0
0x3212  ldloc.0
0x3213  brfalse.s loc_3217
0x3215  ldloc.0
0x3216  ret
0x3217  ldarg.1
0x3218  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x321d  stloc.1
0x321e  ldloc.1
0x321f  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x3224  ldc.i4.1
0x3225  ldarg.0
0x3226  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sdk.InProcessCrmService::_organizationId
0x322b  newobj   instance void Microsoft.Crm.Sdk.Crm2007.Request::.ctor(string requestName, bool returnDynamicEntities, valuetype [mscorlib]System.Guid organizationId)
0x3230  stloc.0
0x3231  ldloc.0
0x3232  callvirt instance class Microsoft.Crm.Sdk.IRequestBuilder Microsoft.Crm.Sdk.RequestBase::get_RequestBuilder()
0x3237  callvirt instance class Microsoft.Crm.Sdk.RequestFieldDescription[] Microsoft.Crm.Sdk.IRequestBuilder::get_Fields()
0x323c  stloc.3
0x323d  ldc.i4.0
0x323e  stloc.s  4
0x3240  br.s     loc_32BF
0x3242  ldloc.3
0x3243  ldloc.s  4
0x3245  ldelem.ref
0x3246  stloc.s  5
0x3248  ldloc.s  5
0x324a  callvirt instance string Microsoft.Crm.Sdk.RequestFieldDescription::get_Name()
0x324f  stloc.s  6
0x3251  ldloc.s  5
0x3253  callvirt instance string Microsoft.Crm.Sdk.RequestFieldDescription::get_PublicName()
0x3258  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x325d  brtrue.s loc_3268
0x325f  ldloc.s  5
0x3261  callvirt instance string Microsoft.Crm.Sdk.RequestFieldDescription::get_PublicName()
0x3266  stloc.s  6
0x3268  ldloc.1
0x3269  ldloc.s  6
0x326b  callvirt instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string)
0x3270  ldarg.1
0x3271  ldnull
0x3272  callvirt instance object [mscorlib]System.Reflection.PropertyInfo::GetValue(object, object[])
0x3277  stloc.s  7
0x3279  ldloc.s  5
0x327b  callvirt instance class Microsoft.Crm.Sdk.IFieldParser Microsoft.Crm.Sdk.RequestFieldDescription::get_Parser()
0x3280  ldloc.s  7
0x3282  callvirt instance object [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.IFieldExtractor::Extract(object)
0x3287  stloc.s  8
0x3289  ldloc.0
0x328a  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyBag Microsoft.Crm.Sdk.RequestBase::get_InputParameters()
0x328f  ldloc.s  5
0x3291  callvirt instance string Microsoft.Crm.Sdk.RequestFieldDescription::get_Name()
0x3296  ldloc.s  8
0x3298  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyBag::set_Item(string, object)
0x329d  ldloc.s  5
0x329f  callvirt instance class Microsoft.Crm.Sdk.IFieldParser Microsoft.Crm.Sdk.RequestFieldDescription::get_Parser()
0x32a4  isinst   Microsoft.Crm.Sdk.ISelectorFieldExtractor
0x32a9  stloc.s  9
0x32ab  ldloc.s  9
0x32ad  brfalse.s loc_32B9
0x32af  ldloc.s  9
0x32b1  ldloc.0
0x32b2  ldloc.s  8
0x32b4  callvirt instance void Microsoft.Crm.Sdk.ISelectorFieldExtractor::SetSelector(class Microsoft.Crm.Sdk.RequestBase request, object fieldValue)
0x32b9  ldloc.s  4
0x32bb  ldc.i4.1
0x32bc  add
0x32bd  stloc.s  4
0x32bf  ldloc.s  4
0x32c1  ldloc.3
0x32c2  ldlen
0x32c3  conv.i4
0x32c4  blt      loc_3242
0x32c9  ldloc.0
0x32ca  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyBag Microsoft.Crm.Sdk.RequestBase::get_InputParameters()
0x32cf  ldstr    aOptionalparame// "OptionalParameters"
0x32d4  ldc.i4.0
0x32d5  newarr   [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter
0x32da  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyBag::set_Item(string, object)
0x32df  ldloc.1
0x32e0  ldstr    aOptionalparame// "OptionalParameters"
0x32e5  callvirt instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string)
0x32ea  ldarg.1
0x32eb  ldnull
0x32ec  callvirt instance object [mscorlib]System.Reflection.PropertyInfo::GetValue(object, object[])
0x32f1  stloc.2
0x32f2  ldloc.2
0x32f3  brfalse.s loc_3306
0x32f5  ldloc.0
0x32f6  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyBag Microsoft.Crm.Sdk.RequestBase::get_InputParameters()
0x32fb  ldstr    aOptionalparame// "OptionalParameters"
0x3300  ldloc.2
0x3301  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyBag::set_Item(string, object)
0x3306  ldloc.0
0x3307  ret
```
