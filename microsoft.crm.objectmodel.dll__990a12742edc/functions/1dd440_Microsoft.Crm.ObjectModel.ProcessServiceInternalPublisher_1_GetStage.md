# Microsoft.Crm.ObjectModel.ProcessServiceInternalPublisher`1::GetStage

- ea: `0x1dd440`
- end: `0x1dd4cf`
- name: `Microsoft.Crm.ObjectModel.ProcessServiceInternalPublisher`1::GetStage`
- size: `143`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callees

- `0x1dd440`

## string_xrefs

- `0x1dd441`: `Create`
- `0x1dd44e`: `Update`
- `0x1dd45b`: `Delete`
- `0x1dd46a`: `createstage`
- `0x1dd477`: `createstage`
- `0x1dd48b`: `updatestage`
- `0x1dd498`: `updatestage`
- `0x1dd4ac`: `deletestage`
- `0x1dd4b9`: `deletestage`

## pseudocode

```c

```

## disassembly

```asm
0x1dd440  ldarg.1
0x1dd441  ldstr    aCreate// "Create"
0x1dd446  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1dd44b  brtrue.s loc_1DD469
0x1dd44d  ldarg.1
0x1dd44e  ldstr    aUpdate// "Update"
0x1dd453  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1dd458  brtrue.s loc_1DD48A
0x1dd45a  ldarg.1
0x1dd45b  ldstr    aDelete// "Delete"
0x1dd460  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1dd465  brtrue.s loc_1DD4AB
0x1dd467  br.s     loc_1DD4CC
0x1dd469  ldarg.0
0x1dd46a  ldstr    aCreatestage// "createstage"
0x1dd46f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1dd474  brfalse.s loc_1DD487
0x1dd476  ldarg.0
0x1dd477  ldstr    aCreatestage// "createstage"
0x1dd47c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1dd481  unbox.any [mscorlib]System.Int32
0x1dd486  ret
0x1dd487  ldc.i4.s 0x28
0x1dd489  ret
0x1dd48a  ldarg.0
0x1dd48b  ldstr    aUpdatestage// "updatestage"
0x1dd490  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1dd495  brfalse.s loc_1DD4A8
0x1dd497  ldarg.0
0x1dd498  ldstr    aUpdatestage// "updatestage"
0x1dd49d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1dd4a2  unbox.any [mscorlib]System.Int32
0x1dd4a7  ret
0x1dd4a8  ldc.i4.s 0x28
0x1dd4aa  ret
0x1dd4ab  ldarg.0
0x1dd4ac  ldstr    aDeletestage// "deletestage"
0x1dd4b1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1dd4b6  brfalse.s loc_1DD4C9
0x1dd4b8  ldarg.0
0x1dd4b9  ldstr    aDeletestage// "deletestage"
0x1dd4be  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1dd4c3  unbox.any [mscorlib]System.Int32
0x1dd4c8  ret
0x1dd4c9  ldc.i4.s 0x28
0x1dd4cb  ret
0x1dd4cc  ldc.i4.s 0x28
0x1dd4ce  ret
```
