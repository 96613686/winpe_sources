# Microsoft.Crm.Extensibility.OData.TypeConverters.EdmComplexTypeConverter::ConvertToCrmTypeInternal

- ea: `0x257f0`
- end: `0x25a86`
- name: `Microsoft.Crm.Extensibility.OData.TypeConverters.EdmComplexTypeConverter::ConvertToCrmTypeInternal`
- size: `662`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x13a00`
- `0x1fa70`
- `0x257f0`
- `0x25a90`
- `0x25b60`
- `0x25db0`
- `0x27ec0`

## string_xrefs

- `0x25906`: `Value passed for the property should be EdmComplexType`
- `0x2597e`: `Microsoft.Crm.Sdk.Messages.ChannelAccessProfilePrivilege`
- `0x25994`: `ChannelAccessProfilePrivilegeId`
- `0x259a3`: `ChannelAccessProfilePrivilegeId`
- `0x259d3`: `PrivilegeDepth`
- `0x259e2`: `PrivilegeDepth`

## pseudocode

```c

```

## disassembly

```asm
0x257f0  ldnull
0x257f1  stloc.0
0x257f2  ldarg.1
0x257f3  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> [System.Web.OData]System.Web.OData.Delta::GetChangedPropertyNames()
0x257f8  stloc.1
0x257f9  ldarg.1
0x257fa  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuredType [System.Web.OData]System.Web.OData.EdmStructuredObject::get_ActualEdmType()
0x257ff  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmComplexType
0x25804  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmComplexType::GetCustomState()
0x25809  castclass [mscorlib]System.Type
0x2580e  stloc.2
0x2580f  ldloc.2
0x25810  ldtoken  [mscorlib]System.Object
0x25815  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2581a  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0x2581f  brfalse  loc_258AF
0x25824  ldarg.1
0x25825  ldnull
0x25826  stloc.3
0x25827  ldnull
0x25828  stloc.s  4
0x2582a  dup
0x2582b  ldstr    aValue_0// "Value"
0x25830  ldloca.s 4
0x25832  callvirt instance bool [System.Web.OData]System.Web.OData.Delta::TryGetPropertyValue(string, object&)
0x25837  pop
0x25838  ldstr    aType_0// "Type"
0x2583d  ldloca.s 3
0x2583f  callvirt instance bool [System.Web.OData]System.Web.OData.Delta::TryGetPropertyValue(string, object&)
0x25844  pop
0x25845  ldloc.3
0x25846  castclass [mscorlib]System.String
0x2584b  stloc.s  5
0x2584d  ldloc.s  4
0x2584f  castclass [mscorlib]System.String
0x25854  stloc.s  6
0x25856  ldloc.s  5
0x25858  ldtoken  [mscorlib]System.Guid
0x2585d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x25862  callvirt instance string [mscorlib]System.Type::get_FullName()
0x25867  callvirt instance bool [mscorlib]System.String::Equals(string)
0x2586c  brfalse.s loc_2587B
0x2586e  ldloc.s  6
0x25870  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Parse(string)
0x25875  box      [mscorlib]System.Guid
0x2587a  ret
0x2587b  ldloc.s  5
0x2587d  ldtoken  [mscorlib]System.DateTimeOffset
0x25882  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x25887  callvirt instance string [mscorlib]System.Type::get_FullName()
0x2588c  callvirt instance bool [mscorlib]System.String::Equals(string)
0x25891  brfalse.s loc_258A0
0x25893  ldloc.s  6
0x25895  call     valuetype [mscorlib]System.DateTimeOffset Microsoft.Crm.Extensibility.OData.CrmODataUtilities::ConvertToDateTimeOffset(object propertyValue)
0x2589a  box      [mscorlib]System.DateTimeOffset
0x2589f  ret
0x258a0  ldloc.s  6
0x258a2  ldloc.s  5
0x258a4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string)
0x258a9  call     object [mscorlib]System.Convert::ChangeType(object, class [mscorlib]System.Type)
0x258ae  ret
0x258af  ldloc.1
0x258b0  call     T0x2B000011
0x258b5  brfalse  loc_25A84
0x258ba  ldnull
0x258bb  ldloc.2
0x258bc  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x258c1  ldstr    aPropertyTypeCa// "Property Type can not be null."
0x258c6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x258cb  ldloc.2
0x258cc  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EdmCollectionProvider::IsCollection(class [mscorlib]System.Type)
0x258d1  brfalse.s loc_258E1
0x258d3  ldarg.0
0x258d4  ldarg.1
0x258d5  ldloc.2
0x258d6  call     instance object Microsoft.Crm.Extensibility.OData.TypeConverters.EdmComplexTypeConverter::GetCollectionOfCollectionCrmType(class [System.Web.OData]System.Web.OData.EdmComplexObject edmTypeValue, class [mscorlib]System.Type clrType)
0x258db  stloc.0
0x258dc  br       loc_25A84
0x258e1  ldloc.2
0x258e2  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EdmCollectionProvider::IsGenericCollectionOfDictionaryType(class [mscorlib]System.Type)
0x258e7  brfalse.s loc_258FE
0x258e9  ldloc.2
0x258ea  ldc.i4.1
0x258eb  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type, bool)
0x258f0  stloc.0
0x258f1  ldarg.0
0x258f2  ldarg.1
0x258f3  ldloc.0
0x258f4  call     instance void Microsoft.Crm.Extensibility.OData.TypeConverters.EdmComplexTypeConverter::PopulateGenericCollectionOfDictionaryCrmType(class [System.Web.OData]System.Web.OData.EdmComplexObject edmTypeValue, object crmTypeObject)
0x258f9  br       loc_25A84
0x258fe  ldarg.1
0x258ff  stloc.s  7
0x25901  ldloc.s  7
0x25903  ldnull
0x25904  cgt.un
0x25906  ldstr    aValuePassedFor// "Value passed for the property should be"...
0x2590b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x25910  ldloc.2
0x25911  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeRequiredLevelManagedProperty
0x25916  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2591b  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x25920  brfalse.s loc_25978
0x25922  ldloc.s  7
0x25924  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuredType [System.Web.OData]System.Web.OData.EdmStructuredObject::get_ActualEdmType()
0x25929  ldstr    aValue_0// "Value"
0x2592e  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuredType::FindProperty(string)
0x25933  ldnull
0x25934  stloc.s  8
0x25936  ldloc.s  7
0x25938  ldstr    aValue_0// "Value"
0x2593d  ldloca.s 8
0x2593f  callvirt instance bool [System.Web.OData]System.Web.OData.Delta::TryGetPropertyValue(string, object&)
0x25944  pop
0x25945  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty::get_Type()
0x2594a  ldarg.0
0x2594b  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.TypeConverters.EdmComplexTypeConverter::edmModel
0x25950  ldnull
0x25951  ldnull
0x25952  ldnull
0x25953  call     class Microsoft.Crm.Extensibility.OData.TypeConverters.IEdmTypeConverter Microsoft.Crm.Extensibility.OData.EdmTypeConverter::GetEdmTypeConverter(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference edmTypeReference, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel, [opt] object clrOrComplexObjectType, [opt] string propertyName, [opt] object propertyValue)
0x25958  ldloc.s  8
0x2595a  callvirt instance object Microsoft.Crm.Extensibility.OData.TypeConverters.IEdmTypeConverter::ConvertToCrmType(object edmTypeValue)
0x2595f  stloc.s  9
0x25961  ldloc.2
0x25962  ldc.i4.1
0x25963  newarr   [mscorlib]System.Object
0x25968  dup
0x25969  ldc.i4.0
0x2596a  ldloc.s  9
0x2596c  stelem.ref
0x2596d  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type, object[])
0x25972  stloc.0
0x25973  br       loc_25A2C
0x25978  ldloc.2
0x25979  callvirt instance string [mscorlib]System.Type::get_FullName()
0x2597e  ldstr    aMicrosoftCrmSd_0// "Microsoft.Crm.Sdk.Messages.ChannelAcces"...
0x25983  callvirt instance bool [mscorlib]System.String::Equals(string)
0x25988  brfalse  loc_25A24
0x2598d  ldloc.s  7
0x2598f  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuredType [System.Web.OData]System.Web.OData.EdmStructuredObject::get_ActualEdmType()
0x25994  ldstr    aChannelaccessp// "ChannelAccessProfilePrivilegeId"
0x25999  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuredType::FindProperty(string)
0x2599e  ldnull
0x2599f  stloc.s  0xA
0x259a1  ldloc.s  7
0x259a3  ldstr    aChannelaccessp// "ChannelAccessProfilePrivilegeId"
0x259a8  ldloca.s 0xA
0x259aa  callvirt instance bool [System.Web.OData]System.Web.OData.Delta::TryGetPropertyValue(string, object&)
0x259af  pop
0x259b0  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty::get_Type()
0x259b5  ldarg.0
0x259b6  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.TypeConverters.EdmComplexTypeConverter::edmModel
0x259bb  ldnull
0x259bc  ldnull
0x259bd  ldnull
0x259be  call     class Microsoft.Crm.Extensibility.OData.TypeConverters.IEdmTypeConverter Microsoft.Crm.Extensibility.OData.EdmTypeConverter::GetEdmTypeConverter(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference edmTypeReference, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel, [opt] object clrOrComplexObjectType, [opt] string propertyName, [opt] object propertyValue)
0x259c3  ldloc.s  0xA
0x259c5  callvirt instance object Microsoft.Crm.Extensibility.OData.TypeConverters.IEdmTypeConverter::ConvertToCrmType(object edmTypeValue)
0x259ca  stloc.s  0xB
0x259cc  ldloc.s  7
0x259ce  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuredType [System.Web.OData]System.Web.OData.EdmStructuredObject::get_ActualEdmType()
0x259d3  ldstr    aPrivilegedepth// "PrivilegeDepth"
0x259d8  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuredType::FindProperty(string)
0x259dd  ldnull
0x259de  stloc.s  0xC
0x259e0  ldloc.s  7
0x259e2  ldstr    aPrivilegedepth// "PrivilegeDepth"
0x259e7  ldloca.s 0xC
0x259e9  callvirt instance bool [System.Web.OData]System.Web.OData.Delta::TryGetPropertyValue(string, object&)
0x259ee  pop
0x259ef  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty::get_Type()
0x259f4  ldarg.0
0x259f5  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.TypeConverters.EdmComplexTypeConverter::edmModel
0x259fa  ldnull
0x259fb  ldnull
0x259fc  ldnull
0x259fd  call     class Microsoft.Crm.Extensibility.OData.TypeConverters.IEdmTypeConverter Microsoft.Crm.Extensibility.OData.EdmTypeConverter::GetEdmTypeConverter(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference edmTypeReference, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel, [opt] object clrOrComplexObjectType, [opt] string propertyName, [opt] object propertyValue)
0x25a02  ldloc.s  0xC
0x25a04  callvirt instance object Microsoft.Crm.Extensibility.OData.TypeConverters.IEdmTypeConverter::ConvertToCrmType(object edmTypeValue)
0x25a09  stloc.s  0xD
0x25a0b  ldloc.2
0x25a0c  ldc.i4.2
0x25a0d  newarr   [mscorlib]System.Object
0x25a12  dup
0x25a13  ldc.i4.0
0x25a14  ldloc.s  0xD
0x25a16  stelem.ref
0x25a17  dup
0x25a18  ldc.i4.1
0x25a19  ldloc.s  0xB
0x25a1b  stelem.ref
0x25a1c  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type, object[])
0x25a21  stloc.0
0x25a22  br.s     loc_25A2C
0x25a24  ldloc.2
0x25a25  ldc.i4.1
0x25a26  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type, bool)
0x25a2b  stloc.0
0x25a2c  ldloc.1
0x25a2d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x25a32  stloc.s  0xE
0x25a34  br.s     loc_25A6D
0x25a36  ldloc.s  0xE
0x25a38  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x25a3d  stloc.s  0xF
0x25a3f  ldnull
0x25a40  stloc.s  0x10
0x25a42  ldloc.s  7
0x25a44  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuredType [System.Web.OData]System.Web.OData.EdmStructuredObject::get_ActualEdmType()
0x25a49  ldloc.s  0xF
0x25a4b  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuredType::FindProperty(string)
0x25a50  stloc.s  0x11
0x25a52  ldloc.s  7
0x25a54  ldloc.s  0xF
0x25a56  ldloca.s 0x10
0x25a58  callvirt instance bool [System.Web.OData]System.Web.OData.Delta::TryGetPropertyValue(string, object&)
0x25a5d  brfalse.s loc_25A6D
0x25a5f  ldarg.0
0x25a60  ldloc.0
0x25a61  ldloc.2
0x25a62  ldloc.s  0xF
0x25a64  ldloc.s  0x10
0x25a66  ldloc.s  0x11
0x25a68  call     instance void Microsoft.Crm.Extensibility.OData.TypeConverters.EdmComplexTypeConverter::SetOrAddToCrmPropertyType(object crmTypeObject, class [mscorlib]System.Type clrType, string propertyName, object edmValue, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty property)
0x25a6d  ldloc.s  0xE
0x25a6f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x25a74  brtrue.s loc_25A36
0x25a76  leave.s  loc_25A84
0x25a78  ldloc.s  0xE
0x25a7a  brfalse.s loc_25A83
0x25a7c  ldloc.s  0xE
0x25a7e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x25a83  endfinally
0x25a84  ldloc.0
0x25a85  ret
```
