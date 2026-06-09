# Microsoft.Crm.Sdk.InProcessCrmService::ConvertToStrongTypedResponse

- ea: `0x3310`
- end: `0x33bb`
- name: `Microsoft.Crm.Sdk.InProcessCrmService::ConvertToStrongTypedResponse`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x2e20`

## callees

- `0x3310`
- `0x4ae0`
- `0x4af0`
- `0x62b0`
- `0x6410`
- `0x6420`

## pseudocode

```c

```

## disassembly

```asm
0x3310  ldarg.1
0x3311  ldstr    aDynamicrespons// "dynamicResponse"
0x3316  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x331b  ldarg.2
0x331c  isinst   Microsoft.Crm.Sdk.RequestBase
0x3321  brfalse.s loc_3325
0x3323  ldarg.1
0x3324  ret
0x3325  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x332a  ldstr    a010// "{0}.{1}, {0}"
0x332f  ldc.i4.2
0x3330  newarr   [mscorlib]System.Object
0x3335  dup
0x3336  ldc.i4.0
0x3337  ldstr    aMicrosoftCrmSd// "Microsoft.Crm.SdkTypeProxy"
0x333c  stelem.ref
0x333d  dup
0x333e  ldc.i4.1
0x333f  ldarg.3
0x3340  callvirt instance string Microsoft.Crm.Sdk.IRequestBuilder::get_ResponseName()
0x3345  stelem.ref
0x3346  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x334b  call     string [Microsoft.Crm.Core]Microsoft.Crm.ProductVersion::GetFullyQualifiedTypeName(string)
0x3350  ldc.i4.1
0x3351  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string, bool)
0x3356  stloc.0
0x3357  ldloc.0
0x3358  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type)
0x335d  stloc.1
0x335e  ldarg.3
0x335f  callvirt instance class Microsoft.Crm.Sdk.ResponseFieldDescription[] Microsoft.Crm.Sdk.IRequestBuilder::get_ResponseFields()
0x3364  stloc.2
0x3365  ldc.i4.0
0x3366  stloc.3
0x3367  br.s     loc_33B3
0x3369  ldloc.2
0x336a  ldloc.3
0x336b  ldelem.ref
0x336c  stloc.s  4
0x336e  ldloc.s  4
0x3370  callvirt instance string Microsoft.Crm.Sdk.ResponseFieldDescription::get_Name()
0x3375  stloc.s  5
0x3377  ldloc.s  4
0x3379  callvirt instance string Microsoft.Crm.Sdk.ResponseFieldDescription::get_PublicName()
0x337e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3383  brtrue.s loc_338E
0x3385  ldloc.s  4
0x3387  callvirt instance string Microsoft.Crm.Sdk.ResponseFieldDescription::get_PublicName()
0x338c  stloc.s  5
0x338e  ldloc.0
0x338f  ldloc.s  5
0x3391  callvirt instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string)
0x3396  ldloc.1
0x3397  ldarg.1
0x3398  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyBag Microsoft.Crm.Sdk.ResponseBase::get_OutPuts()
0x339d  ldloc.s  4
0x339f  callvirt instance string Microsoft.Crm.Sdk.ResponseFieldDescription::get_Name()
0x33a4  callvirt instance object [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyBag::get_Item(string)
0x33a9  ldnull
0x33aa  callvirt instance void [mscorlib]System.Reflection.PropertyInfo::SetValue(object, object, object[])
0x33af  ldloc.3
0x33b0  ldc.i4.1
0x33b1  add
0x33b2  stloc.3
0x33b3  ldloc.3
0x33b4  ldloc.2
0x33b5  ldlen
0x33b6  conv.i4
0x33b7  blt.s    loc_3369
0x33b9  ldloc.1
0x33ba  ret
```
