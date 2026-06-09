# Microsoft.Crm.Sdk.ServiceDescription::ExpandRequestForFilter

- ea: `0x8e90`
- end: `0x8f9c`
- name: `Microsoft.Crm.Sdk.ServiceDescription::ExpandRequestForFilter`
- size: `268`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `service_task, broker_com_uri`

## callers

- `0x8bf0`

## callees

- `0x5d40`
- `0x5d50`
- `0x5ef0`
- `0x5f10`
- `0x5f20`
- `0x5f40`
- `0x5fb0`
- `0x5fc0`
- `0x5fd0`
- `0x6000`
- `0x6030`
- `0x6040`
- `0x6190`
- `0x6540`
- `0x6560`
- `0x8740`
- `0x8ba0`
- `0x8e90`
- `0x8fa0`
- `0x9480`

## pseudocode

```c

```

## disassembly

```asm
0x8e90  ldarg.0
0x8e91  ldarg.2
0x8e92  call     instance string[] Microsoft.Crm.Sdk.ServiceDescription::ExtractEntities(class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFilterType filter)
0x8e97  stloc.0
0x8e98  leave.s  loc_8EA0
0x8e9a  pop
0x8e9b  leave    loc_8F9B
0x8ea0  ldarg.1
0x8ea1  callvirt instance class Microsoft.Crm.Sdk.RequestDescription Microsoft.Crm.Sdk.RequestDescription::Clone()
0x8ea6  stloc.1
0x8ea7  ldloc.1
0x8ea8  ldloc.0
0x8ea9  ldloc.1
0x8eaa  callvirt instance string Microsoft.Crm.Sdk.RequestDescription::get_Name()
0x8eaf  ldstr    aRequest// "Request"
0x8eb4  ldsfld   string [mscorlib]System.String::Empty
0x8eb9  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x8ebe  call     string Microsoft.Crm.Sdk.ServiceDescription::ReplaceTokens(string[] entityNames, string elementName)
0x8ec3  callvirt instance void Microsoft.Crm.Sdk.RequestDescription::set_Name(string value)
0x8ec8  ldloc.1
0x8ec9  ldloc.0
0x8eca  ldloc.1
0x8ecb  callvirt instance string Microsoft.Crm.Sdk.RequestDescription::get_PublicName()
0x8ed0  ldstr    aRequest// "Request"
0x8ed5  ldsfld   string [mscorlib]System.String::Empty
0x8eda  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x8edf  call     string Microsoft.Crm.Sdk.ServiceDescription::ReplaceTokens(string[] entityNames, string elementName)
0x8ee4  callvirt instance void Microsoft.Crm.Sdk.RequestDescription::set_PublicName(string value)
0x8ee9  ldloc.1
0x8eea  newobj   instance void [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFiltersType::.ctor()
0x8eef  callvirt instance void Microsoft.Crm.Sdk.RequestDescription::set_Filters(class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFiltersType value)
0x8ef4  ldloc.1
0x8ef5  callvirt instance class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFiltersType Microsoft.Crm.Sdk.RequestDescription::get_Filters()
0x8efa  ldarg.2
0x8efb  callvirt instance class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFilterType [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFiltersType::Add(class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFilterType)
0x8f00  pop
0x8f01  ldloc.1
0x8f02  callvirt instance class Microsoft.Crm.Sdk.RequestFieldDescription[] Microsoft.Crm.Sdk.RequestDescription::get_Fields()
0x8f07  stloc.s  4
0x8f09  ldc.i4.0
0x8f0a  stloc.s  5
0x8f0c  br.s     loc_8F2F
0x8f0e  ldloc.s  4
0x8f10  ldloc.s  5
0x8f12  ldelem.ref
0x8f13  stloc.s  6
0x8f15  ldloc.s  6
0x8f17  ldloc.0
0x8f18  ldloc.s  6
0x8f1a  callvirt instance string Microsoft.Crm.Sdk.RequestFieldDescription::get_PublicName()
0x8f1f  call     string Microsoft.Crm.Sdk.ServiceDescription::ReplaceTokens(string[] entityNames, string elementName)
0x8f24  callvirt instance void Microsoft.Crm.Sdk.RequestFieldDescription::set_PublicName(string value)
0x8f29  ldloc.s  5
0x8f2b  ldc.i4.1
0x8f2c  add
0x8f2d  stloc.s  5
0x8f2f  ldloc.s  5
0x8f31  ldloc.s  4
0x8f33  ldlen
0x8f34  conv.i4
0x8f35  blt.s    loc_8F0E
0x8f37  ldloc.1
0x8f38  callvirt instance class Microsoft.Crm.Sdk.ResponseDescription Microsoft.Crm.Sdk.RequestDescription::get_ResponseDescription()
0x8f3d  ldloc.0
0x8f3e  ldloc.1
0x8f3f  callvirt instance class Microsoft.Crm.Sdk.ResponseDescription Microsoft.Crm.Sdk.RequestDescription::get_ResponseDescription()
0x8f44  callvirt instance string Microsoft.Crm.Sdk.ResponseDescription::get_Name()
0x8f49  ldstr    aResponse// "Response"
0x8f4e  ldsfld   string [mscorlib]System.String::Empty
0x8f53  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x8f58  call     string Microsoft.Crm.Sdk.ServiceDescription::ReplaceTokens(string[] entityNames, string elementName)
0x8f5d  callvirt instance void Microsoft.Crm.Sdk.ResponseDescription::set_Name(string value)
0x8f62  ldarg.0
0x8f63  ldloc.1
0x8f64  callvirt instance class Microsoft.Crm.Sdk.ResponseDescription Microsoft.Crm.Sdk.RequestDescription::get_ResponseDescription()
0x8f69  call     instance void Microsoft.Crm.Sdk.ServiceDescription::SetResponseFields(class Microsoft.Crm.Sdk.ResponseDescription response)
0x8f6e  ldarg.0
0x8f6f  ldfld    class Microsoft.Crm.Sdk.EntityMetadatas Microsoft.Crm.Sdk.ServiceDescription::_entityMetadatas
0x8f74  ldarg.2
0x8f75  callvirt instance int32 [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessageFilterType::get_PrimaryObjectTypeCode()
0x8f7a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Sdk.EntityMetadatas::GetEntity(int32 objectTypeCode)
0x8f7f  stloc.2
0x8f80  ldloc.1
0x8f81  ldloc.2
0x8f82  callvirt instance void Microsoft.Crm.Sdk.RequestDescription::AssociateWithEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entity)
0x8f87  ldloc.1
0x8f88  call     string Microsoft.Crm.Sdk.RequestDescription::GetKey(class Microsoft.Crm.Sdk.RequestDescription request)
0x8f8d  stloc.3
0x8f8e  ldarg.0
0x8f8f  ldfld    class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Sdk.ServiceDescription::_requests
0x8f94  ldloc.3
0x8f95  ldloc.1
0x8f96  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x8f9b  ret
```
