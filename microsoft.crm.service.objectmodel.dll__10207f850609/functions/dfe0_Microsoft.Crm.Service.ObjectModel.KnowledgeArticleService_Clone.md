# Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::Clone

- ea: `0xdfe0`
- end: `0xe0e8`
- name: `Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::Clone`
- size: `264`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0xdfe0`

## string_xrefs

- `0xe08c`: `updatecontent`
- `0xe060`: `publishstatusid`
- `0xe01e`: `expirationstatusid`
- `0xe034`: `isreadyforreview`
- `0xe04a`: `processid`
- `0xe06b`: `scheduledstatusid`

## pseudocode

```c

```

## disassembly

```asm
0xdfe0  ldarg.1
0xdfe1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0xdfe6  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0xdfeb  ldarg.3
0xdfec  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xdff1  stloc.0
0xdff2  ldloc.0
0xdff3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0xdff8  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddAllColumns()
0xdffd  ldarg.0
0xdffe  ldarg.1
0xdfff  ldloc.0
0xe000  ldarg.3
0xe001  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xe006  stloc.1
0xe007  ldloc.1
0xe008  ldstr    aExpirationdate// "expirationdate"
0xe00d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::ClearAttribute(string)
0xe012  ldloc.1
0xe013  ldstr    aExpirationstat// "expirationstateid"
0xe018  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::ClearAttribute(string)
0xe01d  ldloc.1
0xe01e  ldstr    aExpirationstat_0// "expirationstatusid"
0xe023  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::ClearAttribute(string)
0xe028  ldloc.1
0xe029  ldstr    aExpiredreviewo// "expiredreviewoptions"
0xe02e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::ClearAttribute(string)
0xe033  ldloc.1
0xe034  ldstr    aIsreadyforrevi// "isreadyforreview"
0xe039  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::ClearAttribute(string)
0xe03e  ldloc.1
0xe03f  ldstr    aKnowledgeartic_1// "knowledgearticleviews"
0xe044  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::ClearAttribute(string)
0xe049  ldloc.1
0xe04a  ldstr    aProcessid// "processid"
0xe04f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::ClearAttribute(string)
0xe054  ldloc.1
0xe055  ldstr    aPublishon// "publishon"
0xe05a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::ClearAttribute(string)
0xe05f  ldloc.1
0xe060  ldstr    aPublishstatusi// "publishstatusid"
0xe065  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::ClearAttribute(string)
0xe06a  ldloc.1
0xe06b  ldstr    aScheduledstatu// "scheduledstatusid"
0xe070  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::ClearAttribute(string)
0xe075  ldloc.1
0xe076  ldstr    aStageid// "stageid"
0xe07b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::ClearAttribute(string)
0xe080  ldloc.1
0xe081  ldstr    aStatuscode// "statuscode"
0xe086  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::ClearAttribute(string)
0xe08b  ldloc.1
0xe08c  ldstr    aUpdatecontent// "updatecontent"
0xe091  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::ClearAttribute(string)
0xe096  ldloc.1
0xe097  ldarg.2
0xe098  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::Clone(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CloneOptions)
0xe09d  stloc.2
0xe09e  ldloc.2
0xe09f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0xe0a4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0xe0a9  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PlatformName()
0xe0ae  stloc.3
0xe0af  ldloc.2
0xe0b0  ldloc.3
0xe0b1  ldnull
0xe0b2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xe0b7  ldloc.2
0xe0b8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0xe0bd  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsImportable()
0xe0c2  brfalse.s loc_E0D0
0xe0c4  ldloc.2
0xe0c5  ldstr    aImportsequence// "importsequencenumber"
0xe0ca  ldnull
0xe0cb  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xe0d0  ldloc.2
0xe0d1  ldstr    aIsprimary// "isprimary"
0xe0d6  ldloc.1
0xe0d7  ldstr    aIsprimary// "isprimary"
0xe0dc  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xe0e1  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xe0e6  ldloc.2
0xe0e7  ret
```
