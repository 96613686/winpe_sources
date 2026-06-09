# Microsoft.Crm.ObjectModel.WorkflowProcessServiceInternalHandler`1::SetStageValuesIfSynchronousWorkflow

- ea: `0x1e1b70`
- end: `0x1e1c19`
- name: `Microsoft.Crm.ObjectModel.WorkflowProcessServiceInternalHandler`1::SetStageValuesIfSynchronousWorkflow`
- size: `169`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1e1b70`

## string_xrefs

- `0x1e1b7e`: `triggeroncreate`
- `0x1e1be6`: `triggerondelete`
- `0x1e1bb2`: `triggeronupdateattributelist`
- `0x1e1b90`: `createstage`
- `0x1e1b96`: `createstage`
- `0x1e1bc4`: `updatestage`
- `0x1e1bca`: `updatestage`
- `0x1e1bf8`: `deletestage`
- `0x1e1bfe`: `deletestage`

## pseudocode

```c

```

## disassembly

```asm
0x1e1b70  ldarg.0
0x1e1b71  ldarg.1
0x1e1b72  call     instance bool class Microsoft.Crm.ObjectModel.ProcessServiceInternalHandler`1<var<u1>>::IsSyncWorkflow(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0x1e1b77  brfalse  loc_1E1C18
0x1e1b7c  ldarg.0
0x1e1b7d  ldarg.1
0x1e1b7e  ldstr    aTriggeroncreat// "triggeroncreate"
0x1e1b83  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1e1b88  call     instance bool class Microsoft.Crm.ObjectModel.WorkflowProcessServiceInternalHandler`1<var<u1>>::BoolAttributeExistsAndIsTrue(object)
0x1e1b8d  brfalse.s loc_1E1BB0
0x1e1b8f  ldarg.1
0x1e1b90  ldstr    aCreatestage// "createstage"
0x1e1b95  ldarg.1
0x1e1b96  ldstr    aCreatestage// "createstage"
0x1e1b9b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1e1ba0  dup
0x1e1ba1  brtrue.s loc_1E1BAB
0x1e1ba3  pop
0x1e1ba4  ldc.i4.s 0x28
0x1e1ba6  box      [mscorlib]System.Int32
0x1e1bab  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x1e1bb0  ldarg.0
0x1e1bb1  ldarg.1
0x1e1bb2  ldstr    aTriggeronupdat// "triggeronupdateattributelist"
0x1e1bb7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1e1bbc  call     instance bool class Microsoft.Crm.ObjectModel.WorkflowProcessServiceInternalHandler`1<var<u1>>::StringAttributeExistsAndIsNotEmpty(object)
0x1e1bc1  brfalse.s loc_1E1BE4
0x1e1bc3  ldarg.1
0x1e1bc4  ldstr    aUpdatestage// "updatestage"
0x1e1bc9  ldarg.1
0x1e1bca  ldstr    aUpdatestage// "updatestage"
0x1e1bcf  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1e1bd4  dup
0x1e1bd5  brtrue.s loc_1E1BDF
0x1e1bd7  pop
0x1e1bd8  ldc.i4.s 0x28
0x1e1bda  box      [mscorlib]System.Int32
0x1e1bdf  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x1e1be4  ldarg.0
0x1e1be5  ldarg.1
0x1e1be6  ldstr    aTriggerondelet// "triggerondelete"
0x1e1beb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1e1bf0  call     instance bool class Microsoft.Crm.ObjectModel.WorkflowProcessServiceInternalHandler`1<var<u1>>::BoolAttributeExistsAndIsTrue(object)
0x1e1bf5  brfalse.s loc_1E1C18
0x1e1bf7  ldarg.1
0x1e1bf8  ldstr    aDeletestage// "deletestage"
0x1e1bfd  ldarg.1
0x1e1bfe  ldstr    aDeletestage// "deletestage"
0x1e1c03  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1e1c08  dup
0x1e1c09  brtrue.s loc_1E1C13
0x1e1c0b  pop
0x1e1c0c  ldc.i4.s 0x14
0x1e1c0e  box      [mscorlib]System.Int32
0x1e1c13  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x1e1c18  ret
```
