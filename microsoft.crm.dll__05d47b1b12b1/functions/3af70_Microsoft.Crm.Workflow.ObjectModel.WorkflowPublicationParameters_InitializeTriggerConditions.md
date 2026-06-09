# Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::InitializeTriggerConditions

- ea: `0x3af70`
- end: `0x3b004`
- name: `Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::InitializeTriggerConditions`
- size: `148`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x3a460`
- `0x3a570`
- `0x3add0`

## callees

- `0x3ac20`
- `0x3acd0`
- `0x3af70`
- `0x3b060`

## string_xrefs

- `0x3af76`: `triggeroncreate`
- `0x3af83`: `triggeroncreate`
- `0x3afa1`: `triggerondelete`
- `0x3afae`: `triggerondelete`
- `0x3afcc`: `triggeronupdateattributelist`
- `0x3afd9`: `triggeronupdateattributelist`

## pseudocode

```c

```

## disassembly

```asm
0x3af70  ldarg.1
0x3af71  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x3af76  ldstr    aTriggeroncreat// "triggeroncreate"
0x3af7b  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x3af80  brfalse.s loc_3AF94
0x3af82  ldarg.1
0x3af83  ldstr    aTriggeroncreat// "triggeroncreate"
0x3af88  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x3af8d  unbox.any [mscorlib]System.Boolean
0x3af92  brtrue.s loc_3AF9B
0x3af94  ldarg.0
0x3af95  ldc.i4.2
0x3af96  call     instance void Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::RemoveTriggerCondition(valuetype Microsoft.Crm.Workflow.ObjectModel.WorkflowTriggerConditions condition)
0x3af9b  ldarg.1
0x3af9c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x3afa1  ldstr    aTriggerondelet// "triggerondelete"
0x3afa6  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x3afab  brfalse.s loc_3AFC6
0x3afad  ldarg.1
0x3afae  ldstr    aTriggerondelet// "triggerondelete"
0x3afb3  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x3afb8  unbox.any [mscorlib]System.Boolean
0x3afbd  brfalse.s loc_3AFC6
0x3afbf  ldarg.0
0x3afc0  ldc.i4.4
0x3afc1  call     instance void Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::AddTriggerCondition(valuetype Microsoft.Crm.Workflow.ObjectModel.WorkflowTriggerConditions condition)
0x3afc6  ldarg.1
0x3afc7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x3afcc  ldstr    aTriggeronupdat// "triggeronupdateattributelist"
0x3afd1  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x3afd6  brfalse.s loc_3B003
0x3afd8  ldarg.1
0x3afd9  ldstr    aTriggeronupdat// "triggeronupdateattributelist"
0x3afde  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x3afe3  isinst   [mscorlib]System.String
0x3afe8  stloc.0
0x3afe9  ldloc.0
0x3afea  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3afef  brtrue.s loc_3B003
0x3aff1  ldloc.0
0x3aff2  ldc.i4.s 0x2C
0x3aff4  ldc.i4.s 0x3B
0x3aff6  callvirt instance string [mscorlib]System.String::Replace(char, char)
0x3affb  stloc.0
0x3affc  ldarg.0
0x3affd  ldloc.0
0x3affe  call     instance void Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::set_UpdateAttributeList(string value)
0x3b003  ret
```
