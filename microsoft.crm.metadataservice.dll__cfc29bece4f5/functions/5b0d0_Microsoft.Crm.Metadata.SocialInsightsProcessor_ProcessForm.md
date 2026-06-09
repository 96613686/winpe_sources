# Microsoft.Crm.Metadata.SocialInsightsProcessor::ProcessForm

- ea: `0x5b0d0`
- end: `0x5b153`
- name: `Microsoft.Crm.Metadata.SocialInsightsProcessor::ProcessForm`
- size: `131`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x5b0d0`
- `0x5b160`
- `0x5b180`
- `0x5b200`
- `0x5b350`

## string_xrefs

- `0x5b0e3`: `formxml`
- `0x5b101`: `//control[@classid="{86B9E25E-695E-4FEF-AC69-F05CFA96739C}"]`

## pseudocode

```c

```

## disassembly

```asm
0x5b0d0  ldarg.2
0x5b0d1  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5b0d6  stloc.0
0x5b0d7  ldarg.0
0x5b0d8  ldarg.2
0x5b0d9  call     bool Microsoft.Crm.Metadata.SocialInsightsProcessor::ShouldSkipProcessing(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity form, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5b0de  brfalse.s loc_5B0E2
0x5b0e0  leave.s  loc_5B152
0x5b0e2  ldarg.0
0x5b0e3  ldstr    aFormxml// "formxml"
0x5b0e8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x5b0ed  castclass [mscorlib]System.String
0x5b0f2  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x5b0f7  stloc.1
0x5b0f8  ldarg.1
0x5b0f9  call     bool Microsoft.Crm.Metadata.SocialInsightsProcessor::IsForm(int32 objectTypeCode)
0x5b0fe  brfalse.s loc_5B114
0x5b100  ldloc.1
0x5b101  ldstr    aControlClassid// "//control[@classid=\"{86B9E25E-695E-4FE"...
0x5b106  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x5b10b  brfalse.s loc_5B114
0x5b10d  ldarg.1
0x5b10e  ldarg.2
0x5b10f  call     void Microsoft.Crm.Metadata.SocialInsightsProcessor::CreateRelationshipToSocialInsightsIfNotExists(int32 thisEntityTypeCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5b114  ldarg.0
0x5b115  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x5b11a  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x5b11f  ldc.i4   0x406
0x5b124  beq.s    loc_5B12D
0x5b126  ldstr    aUserformid// "userformid"
0x5b12b  br.s     loc_5B132
0x5b12d  ldstr    aFormid// "formid"
0x5b132  stloc.2
0x5b133  ldarg.0
0x5b134  ldloc.2
0x5b135  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x5b13a  unbox.any [mscorlib]System.Guid
0x5b13f  ldloc.1
0x5b140  ldarg.2
0x5b141  call     void Microsoft.Crm.Metadata.SocialInsightsProcessor::CleanupSocialInsightsForRemovedControls(valuetype [mscorlib]System.Guid formId, class [System.Xml]System.Xml.XmlDocument document, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5b146  leave.s  loc_5B152
0x5b148  ldloc.0
0x5b149  brfalse.s loc_5B151
0x5b14b  ldloc.0
0x5b14c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5b151  endfinally
0x5b152  ret
```
