# Microsoft.Crm.Sdk.ServiceDescription::LoadMessage

- ea: `0x8bf0`
- end: `0x8e83`
- name: `Microsoft.Crm.Sdk.ServiceDescription::LoadMessage`
- size: `659`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x88e0`

## callees

- `0x5f20`
- `0x5fc0`
- `0x6000`
- `0x6190`
- `0x8bf0`
- `0x8e90`
- `0x8fa0`
- `0x8fd0`
- `0x9480`

## string_xrefs

- `0x8dfa`: `CreateUoMScheduleRequest`

## pseudocode

```c

```

## disassembly

```asm
0x8bf0  ldarg.1
0x8bf1  callvirt instance class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessagePairsType [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType::get_SdkMessagePairs()
0x8bf6  callvirt instance class [mscorlib]System.Collections.IEnumerator [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessagePairsType::GetEnumerator()
0x8bfb  stloc.0
0x8bfc  br       loc_8E61
0x8c01  ldloc.0
0x8c02  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x8c07  castclass [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessagePairType
0x8c0c  stloc.1
0x8c0d  ldarg.0
0x8c0e  ldarg.1
0x8c0f  ldloc.1
0x8c10  call     instance class Microsoft.Crm.Sdk.RequestDescription Microsoft.Crm.Sdk.ServiceDescription::CreateRequestDescription(class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType message, class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessagePairType pair)
0x8c15  stloc.2
0x8c16  ldarg.1
0x8c17  callvirt instance bool [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType::get_Template()
0x8c1c  brfalse.s loc_8C63
0x8c1e  ldarg.1
0x8c1f  callvirt instance class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFiltersType [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType::get_SdkMessageFilters()
0x8c24  callvirt instance class [mscorlib]System.Collections.IEnumerator [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFiltersType::GetEnumerator()
0x8c29  stloc.3
0x8c2a  br.s     loc_8C42
0x8c2c  ldloc.3
0x8c2d  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x8c32  castclass [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFilterType
0x8c37  stloc.s  4
0x8c39  ldarg.0
0x8c3a  ldloc.2
0x8c3b  ldloc.s  4
0x8c3d  call     instance void Microsoft.Crm.Sdk.ServiceDescription::ExpandRequestForFilter(class Microsoft.Crm.Sdk.RequestDescription request, class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFilterType messageFilter)
0x8c42  ldloc.3
0x8c43  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8c48  brtrue.s loc_8C2C
0x8c4a  leave    loc_8E61
0x8c4f  ldloc.3
0x8c50  isinst   [mscorlib]System.IDisposable
0x8c55  stloc.s  5
0x8c57  ldloc.s  5
0x8c59  brfalse.s loc_8C62
0x8c5b  ldloc.s  5
0x8c5d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8c62  endfinally
0x8c63  ldarg.1
0x8c64  callvirt instance string [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType::get_CategoryName()
0x8c69  brfalse  loc_8D7D
0x8c6e  ldarg.1
0x8c6f  callvirt instance string [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType::get_CategoryName()
0x8c74  callvirt instance int32 [mscorlib]System.String::get_Length()
0x8c79  ldc.i4.0
0x8c7a  ble      loc_8D7D
0x8c7f  ldarg.1
0x8c80  callvirt instance string [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType::get_CategoryName()
0x8c85  ldstr    aNone// "None"
0x8c8a  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x8c8f  brfalse  loc_8D7D
0x8c94  ldarg.1
0x8c95  callvirt instance bool [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType::get_Expand()
0x8c9a  brfalse  loc_8D62
0x8c9f  ldarg.1
0x8ca0  callvirt instance class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFiltersType [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType::get_SdkMessageFilters()
0x8ca5  callvirt instance class [mscorlib]System.Collections.IEnumerator [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFiltersType::GetEnumerator()
0x8caa  stloc.3
0x8cab  br       loc_8D41
0x8cb0  ldloc.3
0x8cb1  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x8cb6  castclass [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFilterType
0x8cbb  stloc.s  7
0x8cbd  ldloc.s  7
0x8cbf  callvirt instance bool [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFilterType::get_IsVisible()
0x8cc4  brfalse.s loc_8D41
0x8cc6  nop
0x8cc7  ldarg.0
0x8cc8  ldfld    class Microsoft.Crm.Sdk.EntityMetadatas Microsoft.Crm.Sdk.ServiceDescription::_entityMetadatas
0x8ccd  ldloc.s  7
0x8ccf  callvirt instance int32 [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFilterType::get_PrimaryObjectTypeCode()
0x8cd4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Sdk.EntityMetadatas::GetEntity(int32 objectTypeCode)
0x8cd9  stloc.s  8
0x8cdb  leave.s  loc_8CE0
0x8cdd  pop
0x8cde  leave.s  loc_8D41
0x8ce0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8ce5  ldstr    aTarget01// "Target{0}{1}"
0x8cea  ldc.i4.2
0x8ceb  newarr   [mscorlib]System.Object
0x8cf0  dup
0x8cf1  ldc.i4.0
0x8cf2  ldarg.1
0x8cf3  callvirt instance string [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType::get_CategoryName()
0x8cf8  stelem.ref
0x8cf9  dup
0x8cfa  ldc.i4.1
0x8cfb  ldloc.s  8
0x8cfd  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x8d02  stelem.ref
0x8d03  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8d08  stloc.s  9
0x8d0a  ldarg.0
0x8d0b  ldfld    class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Sdk.ServiceDescription::_targetNameToEntity
0x8d10  ldloc.s  9
0x8d12  ldloc.s  8
0x8d14  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x8d19  ldarg.0
0x8d1a  ldfld    class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Sdk.ServiceDescription::_entities
0x8d1f  ldloc.s  8
0x8d21  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x8d26  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x8d2b  brtrue.s loc_8D41
0x8d2d  ldarg.0
0x8d2e  ldfld    class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Sdk.ServiceDescription::_entities
0x8d33  ldloc.s  8
0x8d35  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x8d3a  ldloc.s  8
0x8d3c  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x8d41  ldloc.3
0x8d42  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8d47  brtrue   loc_8CB0
0x8d4c  leave.s  loc_8D62
0x8d4e  ldloc.3
0x8d4f  isinst   [mscorlib]System.IDisposable
0x8d54  stloc.s  5
0x8d56  ldloc.s  5
0x8d58  brfalse.s loc_8D61
0x8d5a  ldloc.s  5
0x8d5c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8d61  endfinally
0x8d62  ldloc.2
0x8d63  call     string Microsoft.Crm.Sdk.RequestDescription::GetKey(class Microsoft.Crm.Sdk.RequestDescription request)
0x8d68  stloc.s  6
0x8d6a  ldarg.0
0x8d6b  ldfld    class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Sdk.ServiceDescription::_requests
0x8d70  ldloc.s  6
0x8d72  ldloc.2
0x8d73  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x8d78  br       loc_8E61
0x8d7d  ldarg.1
0x8d7e  callvirt instance string [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType::get_Name()
0x8d83  stloc.s  0xA
0x8d85  ldarg.1
0x8d86  callvirt instance class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFiltersType [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageType::get_SdkMessageFilters()
0x8d8b  callvirt instance class [mscorlib]System.Collections.IEnumerator [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFiltersType::GetEnumerator()
0x8d90  stloc.3
0x8d91  br       loc_8E2A
0x8d96  ldloc.3
0x8d97  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x8d9c  castclass [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFilterType
0x8da1  stloc.s  0xC
0x8da3  ldloc.s  0xC
0x8da5  callvirt instance int32 [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFilterType::get_PrimaryObjectTypeCode()
0x8daa  brfalse.s loc_8E1C
0x8dac  ldarg.0
0x8dad  ldfld    class Microsoft.Crm.Sdk.EntityMetadatas Microsoft.Crm.Sdk.ServiceDescription::_entityMetadatas
0x8db2  ldloc.s  0xC
0x8db4  callvirt instance int32 [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFilterType::get_PrimaryObjectTypeCode()
0x8db9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Sdk.EntityMetadatas::GetEntity(int32 objectTypeCode)
0x8dbe  stloc.s  0xD
0x8dc0  leave.s  loc_8DC5
0x8dc2  pop
0x8dc3  leave.s  loc_8E2A
0x8dc5  ldloc.2
0x8dc6  callvirt instance string Microsoft.Crm.Sdk.RequestDescription::get_PublicName()
0x8dcb  ldloc.s  0xA
0x8dcd  ldsfld   string [mscorlib]System.String::Empty
0x8dd2  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x8dd7  ldstr    aRequest// "Request"
0x8ddc  ldsfld   string [mscorlib]System.String::Empty
0x8de1  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x8de6  ldloc.s  0xD
0x8de8  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x8ded  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8df2  brtrue.s loc_8E06
0x8df4  ldloc.2
0x8df5  callvirt instance string Microsoft.Crm.Sdk.RequestDescription::get_PublicName()
0x8dfa  ldstr    aCreateuomsched// "CreateUoMScheduleRequest"
0x8dff  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8e04  brfalse.s loc_8E2A
0x8e06  ldarg.0
0x8e07  ldloc.2
0x8e08  callvirt instance class Microsoft.Crm.Sdk.ResponseDescription Microsoft.Crm.Sdk.RequestDescription::get_ResponseDescription()
0x8e0d  call     instance void Microsoft.Crm.Sdk.ServiceDescription::SetResponseFields(class Microsoft.Crm.Sdk.ResponseDescription response)
0x8e12  ldloc.2
0x8e13  ldloc.s  0xD
0x8e15  callvirt instance void Microsoft.Crm.Sdk.RequestDescription::AssociateWithEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entity)
0x8e1a  leave.s  loc_8E4B
0x8e1c  ldarg.0
0x8e1d  ldloc.2
0x8e1e  callvirt instance class Microsoft.Crm.Sdk.ResponseDescription Microsoft.Crm.Sdk.RequestDescription::get_ResponseDescription()
0x8e23  call     instance void Microsoft.Crm.Sdk.ServiceDescription::SetResponseFields(class Microsoft.Crm.Sdk.ResponseDescription response)
0x8e28  leave.s  loc_8E4B
0x8e2a  ldloc.3
0x8e2b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8e30  brtrue   loc_8D96
0x8e35  leave.s  loc_8E4B
0x8e37  ldloc.3
0x8e38  isinst   [mscorlib]System.IDisposable
0x8e3d  stloc.s  5
0x8e3f  ldloc.s  5
0x8e41  brfalse.s loc_8E4A
0x8e43  ldloc.s  5
0x8e45  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8e4a  endfinally
0x8e4b  ldloc.2
0x8e4c  call     string Microsoft.Crm.Sdk.RequestDescription::GetKey(class Microsoft.Crm.Sdk.RequestDescription request)
0x8e51  stloc.s  0xB
0x8e53  ldarg.0
0x8e54  ldfld    class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Sdk.ServiceDescription::_requests
0x8e59  ldloc.s  0xB
0x8e5b  ldloc.2
0x8e5c  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x8e61  ldloc.0
0x8e62  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8e67  brtrue   loc_8C01
0x8e6c  leave.s  loc_8E82
0x8e6e  ldloc.0
0x8e6f  isinst   [mscorlib]System.IDisposable
0x8e74  stloc.s  5
0x8e76  ldloc.s  5
0x8e78  brfalse.s loc_8E81
0x8e7a  ldloc.s  5
0x8e7c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8e81  endfinally
0x8e82  ret
```
