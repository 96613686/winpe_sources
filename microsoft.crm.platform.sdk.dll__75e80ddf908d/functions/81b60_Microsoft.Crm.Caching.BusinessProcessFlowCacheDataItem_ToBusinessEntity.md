# Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::ToBusinessEntity

- ea: `0x81b60`
- end: `0x81d6f`
- name: `Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::ToBusinessEntity`
- size: `527`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `installer_update, broker_com_uri`

## callers

- `0x814e0`

## callees

- `0x81650`
- `0x81660`
- `0x81670`
- `0x81680`
- `0x81690`
- `0x816a0`
- `0x816b0`
- `0x816c0`
- `0x816d0`
- `0x816e0`
- `0x816f0`
- `0x81700`
- `0x81710`
- `0x81720`
- `0x81730`
- `0x81740`
- `0x81750`
- `0x81760`
- `0x81770`
- `0x81780`
- `0x81790`
- `0x817a0`
- `0x817b0`
- `0x817c0`
- `0x817d0`
- `0x9ca70`
- `0x9ce50`

## string_xrefs

- `0x81ca7`: `triggeroncreate`
- `0x81cbd`: `triggerondelete`
- `0x81cd3`: `triggeronupdateattributelist`

## pseudocode

```c

```

## disassembly

```asm
0x81b60  ldstr    aWorkflow// "Workflow"
0x81b65  ldarg.1
0x81b66  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x81b6b  call     class Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.BusinessEntities.EntityClassFactory::CreateInstance(string entityName, valuetype [mscorlib]System.Guid organizationId)
0x81b70  dup
0x81b71  ldstr    aBusinessproces// "businessprocesstype"
0x81b76  ldarg.0
0x81b77  call     instance int32 Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::get_BusinessProcessType()
0x81b7c  box      [mscorlib]System.Int32
0x81b81  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string attributeName, object attributeValue)
0x81b86  dup
0x81b87  ldstr    aClientdata// "clientdata"
0x81b8c  ldarg.0
0x81b8d  call     instance string Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::get_ClientData()
0x81b92  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string attributeName, object attributeValue)
0x81b97  dup
0x81b98  ldstr    aDescription// "description"
0x81b9d  ldarg.0
0x81b9e  call     instance string Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::get_Description()
0x81ba3  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string attributeName, object attributeValue)
0x81ba8  dup
0x81ba9  ldstr    aMode// "mode"
0x81bae  ldarg.0
0x81baf  call     instance int32 Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::get_Mode()
0x81bb4  box      [mscorlib]System.Int32
0x81bb9  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string attributeName, object attributeValue)
0x81bbe  dup
0x81bbf  ldstr    aName_0// "name"
0x81bc4  ldarg.0
0x81bc5  call     instance string Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::get_Name()
0x81bca  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string attributeName, object attributeValue)
0x81bcf  dup
0x81bd0  ldstr    aOndemand// "ondemand"
0x81bd5  ldarg.0
0x81bd6  call     instance bool Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::get_OnDemand()
0x81bdb  box      [mscorlib]System.Boolean
0x81be0  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string attributeName, object attributeValue)
0x81be5  dup
0x81be6  ldstr    aOwnerid// "ownerid"
0x81beb  ldarg.0
0x81bec  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::get_OwnerId()
0x81bf1  box      [mscorlib]System.Guid
0x81bf6  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string attributeName, object attributeValue)
0x81bfb  dup
0x81bfc  ldstr    aOwneridtype// "owneridtype"
0x81c01  ldarg.0
0x81c02  call     instance int32 Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::get_OwnerIdType()
0x81c07  box      [mscorlib]System.Int32
0x81c0c  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string attributeName, object attributeValue)
0x81c11  dup
0x81c12  ldstr    aOwningbusiness// "owningbusinessunit"
0x81c17  ldarg.0
0x81c18  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::get_OwningBusinessUnit()
0x81c1d  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x81c22  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string attributeName, object attributeValue)
0x81c27  dup
0x81c28  ldstr    aPrimaryentity_0// "primaryentity"
0x81c2d  ldarg.0
0x81c2e  call     instance int32 Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::get_PrimaryEntity()
0x81c33  box      [mscorlib]System.Int32
0x81c38  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string attributeName, object attributeValue)
0x81c3d  dup
0x81c3e  ldstr    aProcessorder// "processorder"
0x81c43  ldarg.0
0x81c44  call     instance valuetype [mscorlib]System.Nullable`1<int32> Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::get_ProcessOrder()
0x81c49  box      valuetype [mscorlib]System.Nullable`1<int32>
0x81c4e  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string attributeName, object attributeValue)
0x81c53  dup
0x81c54  ldstr    aProcessroleass// "processroleassignment"
0x81c59  ldarg.0
0x81c5a  call     instance string Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::get_ProcessRoleAssignment()
0x81c5f  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string attributeName, object attributeValue)
0x81c64  dup
0x81c65  ldstr    aScope// "scope"
0x81c6a  ldarg.0
0x81c6b  call     instance int32 Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::get_Scope()
0x81c70  box      [mscorlib]System.Int32
0x81c75  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string attributeName, object attributeValue)
0x81c7a  dup
0x81c7b  ldstr    aStatecode// "statecode"
0x81c80  ldarg.0
0x81c81  call     instance int32 Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::get_StateCode()
0x81c86  box      [mscorlib]System.Int32
0x81c8b  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string attributeName, object attributeValue)
0x81c90  dup
0x81c91  ldstr    aSubprocess// "subprocess"
0x81c96  ldarg.0
0x81c97  call     instance bool Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::get_SubProcess()
0x81c9c  box      [mscorlib]System.Boolean
0x81ca1  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string attributeName, object attributeValue)
0x81ca6  dup
0x81ca7  ldstr    aTriggeroncreat// "triggeroncreate"
0x81cac  ldarg.0
0x81cad  call     instance bool Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::get_TriggerOnCreate()
0x81cb2  box      [mscorlib]System.Boolean
0x81cb7  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string attributeName, object attributeValue)
0x81cbc  dup
0x81cbd  ldstr    aTriggerondelet// "triggerondelete"
0x81cc2  ldarg.0
0x81cc3  call     instance bool Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::get_TriggerOnDelete()
0x81cc8  box      [mscorlib]System.Boolean
0x81ccd  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string attributeName, object attributeValue)
0x81cd2  dup
0x81cd3  ldstr    aTriggeronupdat// "triggeronupdateattributelist"
0x81cd8  ldarg.0
0x81cd9  call     instance string Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::get_TriggerOnUpdateAttributeList()
0x81cde  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string attributeName, object attributeValue)
0x81ce3  dup
0x81ce4  ldstr    aType// "type"
0x81ce9  ldarg.0
0x81cea  call     instance int32 Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::get_Type()
0x81cef  box      [mscorlib]System.Int32
0x81cf4  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string attributeName, object attributeValue)
0x81cf9  dup
0x81cfa  ldstr    aUidata// "uidata"
0x81cff  ldarg.0
0x81d00  call     instance string Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::get_UIData()
0x81d05  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string attributeName, object attributeValue)
0x81d0a  dup
0x81d0b  ldstr    aUniquename_1// "uniquename"
0x81d10  ldarg.0
0x81d11  call     instance string Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::get_UniqueName()
0x81d16  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string attributeName, object attributeValue)
0x81d1b  dup
0x81d1c  ldstr    aVersionnumber// "versionnumber"
0x81d21  ldarg.0
0x81d22  call     instance int64 Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::get_VersionNumber()
0x81d27  box      [mscorlib]System.Int64
0x81d2c  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string attributeName, object attributeValue)
0x81d31  dup
0x81d32  ldstr    aWorkflowid// "workflowid"
0x81d37  ldarg.0
0x81d38  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::get_WorkflowId()
0x81d3d  box      [mscorlib]System.Guid
0x81d42  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string attributeName, object attributeValue)
0x81d47  dup
0x81d48  ldstr    aCategory// "category"
0x81d4d  ldarg.0
0x81d4e  call     instance int32 Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::get_WorkflowCategory()
0x81d53  box      [mscorlib]System.Int32
0x81d58  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string attributeName, object attributeValue)
0x81d5d  dup
0x81d5e  ldstr    aXaml// "xaml"
0x81d63  ldarg.0
0x81d64  call     instance string Microsoft.Crm.Caching.BusinessProcessFlowCacheDataItem::get_Xaml()
0x81d69  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string attributeName, object attributeValue)
0x81d6e  ret
```
