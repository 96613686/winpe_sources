# Microsoft.Crm.BusinessEntities.SecurityExtensionRetrieveMultipleHelper::GetRetrieveMultipleSecurityFilterOption

- ea: `0x72d80`
- end: `0x72e23`
- name: `Microsoft.Crm.BusinessEntities.SecurityExtensionRetrieveMultipleHelper::GetRetrieveMultipleSecurityFilterOption`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x74930`

## callees

- `0x1aa10`
- `0x1e5c0`
- `0x67090`
- `0x67100`
- `0x679e0`
- `0x72c90`
- `0x72ce0`
- `0x72d70`
- `0x72d80`
- `0x72f60`
- `0x72fe0`
- `0x73020`
- `0x73040`

## string_xrefs

- `0x72e05`: `securityQueryDetails`
- `0x72e0a`: `securityOption`

## pseudocode

```c

```

## disassembly

```asm
0x72d80  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x72d85  brfalse.s loc_72D89
0x72d87  ldc.i4.3
0x72d88  ret
0x72d89  ldc.i4.0
0x72d8a  stloc.0
0x72d8b  ldarg.1
0x72d8c  callvirt instance bool Microsoft.Crm.BusinessEntities.ExecutionContext::get_ForceCrm2011DefaultSecurityOption()
0x72d91  brfalse.s loc_72D9B
0x72d93  call     valuetype Microsoft.Crm.BusinessEntities.RetrieveMultipleSecurityFilterOption Microsoft.Crm.BusinessEntities.SecurityExtensionRetrieveMultipleHelper::get_DefaultCrm2011SecurityFilterOption()
0x72d98  stloc.0
0x72d99  br.s     loc_72DCC
0x72d9b  ldarg.0
0x72d9c  callvirt instance valuetype Microsoft.Crm.BusinessEntities.LinkEntityType Microsoft.Crm.BusinessEntities.RetrieveMultipleSecurityFilterPopulatorInitializationData::get_LinkEntityType()
0x72da1  ldc.i4.1
0x72da2  beq.s    loc_72DC1
0x72da4  ldarg.0
0x72da5  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.BusinessEntities.RetrieveMultipleSecurityFilterPopulatorInitializationData::get_ExistingCriteria()
0x72daa  brfalse.s loc_72DC5
0x72dac  ldarg.0
0x72dad  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.BusinessEntities.RetrieveMultipleSecurityFilterPopulatorInitializationData::get_ExistingCriteria()
0x72db2  callvirt instance bool Microsoft.Crm.Query.FilterExpression::get_HasQuickFindFilterInFilterTree()
0x72db7  brfalse.s loc_72DC5
0x72db9  ldarg.1
0x72dba  call     bool Microsoft.Crm.Query.QueryHelper::AreQuickFindOptimizationsEnabled(class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x72dbf  brfalse.s loc_72DC5
0x72dc1  ldc.i4.3
0x72dc2  stloc.0
0x72dc3  br.s     loc_72DCC
0x72dc5  ldarg.1
0x72dc6  call     valuetype Microsoft.Crm.BusinessEntities.RetrieveMultipleSecurityFilterOption Microsoft.Crm.BusinessEntities.SecurityExtensionRetrieveMultipleHelper::GetEnableRetrieveMultipleOptimizationSetting(class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x72dcb  stloc.0
0x72dcc  ldloc.0
0x72dcd  call     bool Microsoft.Crm.BusinessEntities.SecurityExtensionRetrieveMultipleHelper::IsCteBasedRetrieveMultipleSecurityFilterOption(valuetype Microsoft.Crm.BusinessEntities.RetrieveMultipleSecurityFilterOption option)
0x72dd2  brfalse.s loc_72E04
0x72dd4  ldarg.1
0x72dd5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.BusinessEntities.ExecutionContext::get_MetadataCache()
0x72dda  ldstr    aRecordcountsna// "RecordCountSnapshot"
0x72ddf  ldc.i4.0
0x72de0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x72de5  brtrue.s loc_72DEF
0x72de7  call     valuetype Microsoft.Crm.BusinessEntities.RetrieveMultipleSecurityFilterOption Microsoft.Crm.BusinessEntities.SecurityExtensionRetrieveMultipleHelper::get_DefaultCrm2011SecurityFilterOption()
0x72dec  stloc.0
0x72ded  br.s     loc_72E04
0x72def  ldarg.0
0x72df0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.BusinessEntities.RetrieveMultipleSecurityFilterPopulatorInitializationData::get_Metadata()
0x72df5  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x72dfa  ldarg.1
0x72dfb  call     bool Microsoft.Crm.BusinessEntities.SecurityExtensionRetrieveMultipleHelper::DoesRecordCountIndicateOldSecuritySql(int32 objectTypeCode, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x72e00  brfalse.s loc_72E04
0x72e02  ldc.i4.3
0x72e03  stloc.0
0x72e04  ldarg.1
0x72e05  ldstr    aSecurityqueryd// "securityQueryDetails"
0x72e0a  ldstr    aSecurityoption// "securityOption"
0x72e0f  ldloca.s 0
0x72e11  constrained. Microsoft.Crm.BusinessEntities.RetrieveMultipleSecurityFilterOption
0x72e17  callvirt instance string [mscorlib]System.Object::ToString()
0x72e1c  callvirt instance void Microsoft.Crm.BusinessEntities.ExecutionContext::AddToInternalContextVariables(string innerDictionaryKey, string Key, object value)
0x72e21  ldloc.0
0x72e22  ret
```
