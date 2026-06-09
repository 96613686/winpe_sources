# Microsoft.Crm.BusinessEntities.RollupsExtension::TriggerRollup_0

- ea: `0x72450`
- end: `0x724ae`
- name: `Microsoft.Crm.BusinessEntities.RollupsExtension::TriggerRollup_0`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x72240`

## callees

- `0x688c0`
- `0x68910`
- `0x72450`
- `0x724b0`
- `0x84c80`
- `0x85ba0`

## string_xrefs

- `0x72484`: `Update`
- `0x72491`: `Delete`

## pseudocode

```c

```

## disassembly

```asm
0x72450  ldnull
0x72451  stloc.0
0x72452  ldnull
0x72453  stloc.1
0x72454  ldarg.0
0x72455  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x7245a  ldarg.1
0x7245b  ldarg.2
0x7245c  ldarg.0
0x7245d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x72462  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x72467  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x7246c  ldc.i4   0x87
0x72471  ceq
0x72473  call     class Microsoft.Crm.BusinessEntities.Rollup.TriggerPlugin.IRollupTrigger Microsoft.Crm.BusinessEntities.Rollup.TriggerPlugin.RollupTriggerFactory::GetTrigger(class Microsoft.Crm.BusinessEntities.ExecutionContext context, string operation, string primaryEntityName, bool isActivityParty)
0x72478  stloc.2
0x72479  ldloc.2
0x7247a  brfalse.s loc_724AD
0x7247c  ldarg.0
0x7247d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x72482  stloc.0
0x72483  ldarg.1
0x72484  ldstr    aUpdate// "Update"
0x72489  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7248e  brtrue.s loc_7249D
0x72490  ldarg.1
0x72491  ldstr    aDelete// "Delete"
0x72496  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7249b  brfalse.s loc_724A5
0x7249d  ldarg.0
0x7249e  ldloc.2
0x7249f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.BusinessEntities.RollupsExtension::GetPreImage(class Microsoft.Crm.BusinessEntities.ExtensionEventArgs extensionEventArgs, class Microsoft.Crm.BusinessEntities.Rollup.TriggerPlugin.IRollupTrigger rollupTrigger)
0x724a4  stloc.1
0x724a5  ldloc.2
0x724a6  ldloc.1
0x724a7  ldloc.0
0x724a8  callvirt instance void Microsoft.Crm.BusinessEntities.Rollup.TriggerPlugin.IRollupTrigger::Execute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity preImage, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity targetEntity)
0x724ad  ret
```
