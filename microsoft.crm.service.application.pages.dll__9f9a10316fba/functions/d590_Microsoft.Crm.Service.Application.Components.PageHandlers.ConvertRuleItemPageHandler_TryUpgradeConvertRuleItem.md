# Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::TryUpgradeConvertRuleItem

- ea: `0xd590`
- end: `0xd635`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::TryUpgradeConvertRuleItem`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xd240`

## callees

- `0xd590`
- `0xda70`

## pseudocode

```c

```

## disassembly

```asm
0xd590  ldarg.3
0xd591  ldarg.0
0xd592  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xd597  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0xd59c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xd5a1  ldc.i4.0
0xd5a2  ceq
0xd5a4  ldarg.2
0xd5a5  and
0xd5a6  brtrue.s loc_D5AF
0xd5a8  ldstr    asc_15D82// ""
0xd5ad  br.s     loc_D5C0
0xd5af  ldarg.0
0xd5b0  ldarg.0
0xd5b1  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xd5b6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0xd5bb  call     instance string Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::RetrieveWorkflowId(string convertRuleItemId)
0xd5c0  stind.ref
0xd5c1  ldarg.2
0xd5c2  brfalse.s loc_D633
0xd5c4  ldarg.3
0xd5c5  ldind.ref
0xd5c6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xd5cb  brfalse.s loc_D633
0xd5cd  ldarg.0
0xd5ce  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xd5d3  callvirt instance valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormState [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_State()
0xd5d8  ldc.i4.2
0xd5d9  bne.un.s loc_D633
0xd5db  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xd5e0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd5e5  ldarg.1
0xd5e6  ldstr    aSourcechannelt// "sourcechanneltypecode"
0xd5eb  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xd5f0  unbox.any [mscorlib]System.Int32
0xd5f5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0xd5fa  stloc.0
0xd5fb  ldarg.0
0xd5fc  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xd601  ldloc.0
0xd602  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xd607  ldc.i4.1
0xd608  newobj   instance void [Microsoft.Crm.Service.ObjectModel]Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity, string, valuetype [Microsoft.Crm.Service.ObjectModel]Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAction)
0xd60d  stloc.1
0xd60e  ldarg.0
0xd60f  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xd614  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_InnerEntity()
0xd619  stloc.2
0xd61a  ldarg.3
0xd61b  ldloc.1
0xd61c  ldloc.2
0xd61d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Service.ObjectModel]Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::UpgradeConvertRuleItem(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0xd622  stloc.3
0xd623  ldloca.s 3
0xd625  constrained. [mscorlib]System.Guid
0xd62b  callvirt instance string [mscorlib]System.Object::ToString()
0xd630  stind.ref
0xd631  ldc.i4.1
0xd632  ret
0xd633  ldc.i4.0
0xd634  ret
```
