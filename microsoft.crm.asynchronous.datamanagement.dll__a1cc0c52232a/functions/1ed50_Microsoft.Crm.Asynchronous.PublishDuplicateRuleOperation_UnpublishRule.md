# Microsoft.Crm.Asynchronous.PublishDuplicateRuleOperation::UnpublishRule

- ea: `0x1ed50`
- end: `0x1ee18`
- name: `Microsoft.Crm.Asynchronous.PublishDuplicateRuleOperation::UnpublishRule`
- size: `200`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1dc50`
- `0x1dd70`
- `0x1e680`
- `0x1e830`

## callees

- `0x1ea60`
- `0x1ec50`
- `0x1ed50`
- `0x1ee20`
- `0x1ef70`

## pseudocode

```c

```

## disassembly

```asm
0x1ed50  ldarg.0
0x1ed51  ldarg.3
0x1ed52  ldarg.2
0x1ed53  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.PublishDuplicateRuleOperation::GetRuleToPublish(valuetype [mscorlib]System.Guid duplicateRuleId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService crmService, valuetype [mscorlib]System.Guid organizationId)
0x1ed58  stloc.0
0x1ed59  ldloc.0
0x1ed5a  brtrue.s loc_1ED5D
0x1ed5c  ret
0x1ed5d  ldloc.0
0x1ed5e  ldstr    aStatecode// "statecode"
0x1ed63  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1ed68  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x1ed6d  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x1ed72  brtrue.s loc_1ED8C
0x1ed74  ldloc.0
0x1ed75  ldstr    aStatuscode// "statuscode"
0x1ed7a  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1ed7f  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x1ed84  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x1ed89  brtrue.s loc_1ED8C
0x1ed8b  ret
0x1ed8c  ldloc.0
0x1ed8d  ldstr    aBaseentitymatc// "baseentitymatchcodetable"
0x1ed92  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1ed97  castclass [mscorlib]System.String
0x1ed9c  ldarg.1
0x1ed9d  call     void Microsoft.Crm.Asynchronous.PublishDuplicateRuleOperation::DropMatchCodeTable(string tableName, class Microsoft.Crm.Asynchronous.DuplicateRuleDataAccess data)
0x1eda2  ldloc.0
0x1eda3  ldstr    aBaseentitymatc// "baseentitymatchcodetable"
0x1eda8  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1edad  castclass [mscorlib]System.String
0x1edb2  ldloc.0
0x1edb3  ldstr    aMatchingentity_0// "matchingentitymatchcodetable"
0x1edb8  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1edbd  castclass [mscorlib]System.String
0x1edc2  ldc.i4.5
0x1edc3  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x1edc8  brfalse.s loc_1EDE0
0x1edca  ldloc.0
0x1edcb  ldstr    aMatchingentity_0// "matchingentitymatchcodetable"
0x1edd0  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1edd5  castclass [mscorlib]System.String
0x1edda  ldarg.1
0x1eddb  call     void Microsoft.Crm.Asynchronous.PublishDuplicateRuleOperation::DropMatchCodeTable(string tableName, class Microsoft.Crm.Asynchronous.DuplicateRuleDataAccess data)
0x1ede0  ldarg.0
0x1ede1  ldc.i4.0
0x1ede2  ldarg.1
0x1ede3  ldarg.2
0x1ede4  call     void Microsoft.Crm.Asynchronous.PublishDuplicateRuleOperation::SetRuleStatus(valuetype [mscorlib]System.Guid duplicateRuleId, int32 statuscode, class Microsoft.Crm.Asynchronous.DuplicateRuleDataAccess data, valuetype [mscorlib]System.Guid organizationId)
0x1ede9  ldloc.0
0x1edea  ldstr    aBaseentityname// "baseentityname"
0x1edef  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1edf4  castclass [mscorlib]System.String
0x1edf9  ldarg.1
0x1edfa  ldarg.2
0x1edfb  call     void Microsoft.Crm.Asynchronous.PublishDuplicateRuleOperation::RemovePersistMatchcodesAsyncJobIfRequired(string entityName, class Microsoft.Crm.Asynchronous.DuplicateRuleDataAccess data, valuetype [mscorlib]System.Guid organizationId)
0x1ee00  ldloc.0
0x1ee01  ldstr    aMatchingentity// "matchingentityname"
0x1ee06  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1ee0b  castclass [mscorlib]System.String
0x1ee10  ldarg.1
0x1ee11  ldarg.2
0x1ee12  call     void Microsoft.Crm.Asynchronous.PublishDuplicateRuleOperation::RemovePersistMatchcodesAsyncJobIfRequired(string entityName, class Microsoft.Crm.Asynchronous.DuplicateRuleDataAccess data, valuetype [mscorlib]System.Guid organizationId)
0x1ee17  ret
```
