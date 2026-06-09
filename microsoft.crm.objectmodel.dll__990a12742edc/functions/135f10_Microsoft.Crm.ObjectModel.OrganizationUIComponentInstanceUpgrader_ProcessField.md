# Microsoft.Crm.ObjectModel.OrganizationUIComponentInstanceUpgrader::ProcessField

- ea: `0x135f10`
- end: `0x135fe2`
- name: `Microsoft.Crm.ObjectModel.OrganizationUIComponentInstanceUpgrader::ProcessField`
- size: `210`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x19b90`
- `0x135f10`

## string_xrefs

- `0x135f17`: `formxml`
- `0x135f27`: `formxml`
- `0x135f37`: `formxml`
- `0x135f8e`: `formxml`
- `0x135f95`: `formxml`
- `0x135fa5`: `formxml`
- `0x135fb5`: `formxml`

## pseudocode

```c

```

## disassembly

```asm
0x135f10  ldarg.s  5
0x135f12  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x135f17  ldstr    aFormxml// "formxml"
0x135f1c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x135f21  brfalse  loc_135FD2
0x135f26  ldarg.3
0x135f27  ldstr    aFormxml// "formxml"
0x135f2c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x135f31  brtrue   loc_135FD0
0x135f36  ldarg.3
0x135f37  ldstr    aFormxml// "formxml"
0x135f3c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x135f41  castclass [mscorlib]System.String
0x135f46  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x135f4b  brtrue   loc_135FD0
0x135f50  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x135f55  ldarg.s  6
0x135f57  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x135f5c  ldarg.s  6
0x135f5e  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x135f63  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_LanguageCode()
0x135f68  stloc.0
0x135f69  newobj   instance void [Microsoft.Crm.ApplicationBuildUpgrade]Microsoft.Crm.Upgrade.Customization.FormMergeHandler::.ctor()
0x135f6e  stloc.1
0x135f6f  ldloc.1
0x135f70  ldloc.0
0x135f71  callvirt instance void [Microsoft.Crm.ApplicationBuildUpgrade]Microsoft.Crm.Upgrade.Customization.FormMergeHandler::set_LanguageCode(int32)
0x135f76  ldloc.1
0x135f77  ldstr    aFormupgradecon// "FormUpgradeConflictsTabName"
0x135f7c  ldloc.0
0x135f7d  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(int32)
0x135f82  call     string Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string name, class [mscorlib]System.Globalization.CultureInfo culture)
0x135f87  callvirt instance void [Microsoft.Crm.ApplicationBuildUpgrade]Microsoft.Crm.Upgrade.Customization.FormMergeHandler::set_ConflictsTabName(string)
0x135f8c  ldarg.s  4
0x135f8e  ldstr    aFormxml// "formxml"
0x135f93  ldloc.1
0x135f94  ldarg.3
0x135f95  ldstr    aFormxml// "formxml"
0x135f9a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x135f9f  castclass [mscorlib]System.String
0x135fa4  ldarg.2
0x135fa5  ldstr    aFormxml// "formxml"
0x135faa  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x135faf  castclass [mscorlib]System.String
0x135fb4  ldarg.1
0x135fb5  ldstr    aFormxml// "formxml"
0x135fba  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x135fbf  castclass [mscorlib]System.String
0x135fc4  callvirt instance string [Microsoft.Crm.ApplicationBuildUpgrade]Microsoft.Crm.Upgrade.Customization.FormMergeHandler::Upgrade(string, string, string)
0x135fc9  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x135fce  ldc.i4.1
0x135fcf  ret
0x135fd0  ldc.i4.0
0x135fd1  ret
0x135fd2  ldarg.0
0x135fd3  ldarg.1
0x135fd4  ldarg.2
0x135fd5  ldarg.3
0x135fd6  ldarg.s  4
0x135fd8  ldarg.s  5
0x135fda  ldarg.s  6
0x135fdc  call     instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BasicComponentInstanceUpgrader::ProcessField(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x135fe1  ret
```
