# Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStagesAndRunAs

- ea: `0x1e30`
- end: `0x1e8f`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStagesAndRunAs`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1bd0`

## callees

- `0x1e30`

## pseudocode

```c

```

## disassembly

```asm
0x1e30  ldarg.1
0x1e31  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SynchronousWorkflowPublicationParameters
0x1e36  stloc.0
0x1e37  ldloc.0
0x1e38  brfalse.s loc_1E8E
0x1e3a  ldarg.2
0x1e3b  ldc.i4.1
0x1e3c  newarr   [mscorlib]System.Char
0x1e41  dup
0x1e42  ldc.i4.0
0x1e43  ldc.i4.s 0x2C
0x1e45  stelem.i2
0x1e46  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x1e4b  stloc.1
0x1e4c  ldarg.3
0x1e4d  brfalse.s loc_1E5D
0x1e4f  ldloc.0
0x1e50  ldloc.1
0x1e51  ldc.i4.0
0x1e52  ldelem.ref
0x1e53  call     int32 [mscorlib]System.Int32::Parse(string)
0x1e58  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SynchronousWorkflowPublicationParameters::set_CreateStage(int32)
0x1e5d  ldarg.s  4
0x1e5f  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x1e64  brtrue.s loc_1E74
0x1e66  ldloc.0
0x1e67  ldloc.1
0x1e68  ldc.i4.1
0x1e69  ldelem.ref
0x1e6a  call     int32 [mscorlib]System.Int32::Parse(string)
0x1e6f  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SynchronousWorkflowPublicationParameters::set_UpdateStage(int32)
0x1e74  ldarg.s  5
0x1e76  brfalse.s loc_1E86
0x1e78  ldloc.0
0x1e79  ldloc.1
0x1e7a  ldc.i4.2
0x1e7b  ldelem.ref
0x1e7c  call     int32 [mscorlib]System.Int32::Parse(string)
0x1e81  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SynchronousWorkflowPublicationParameters::set_DeleteStage(int32)
0x1e86  ldloc.0
0x1e87  ldarg.s  6
0x1e89  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SynchronousWorkflowPublicationParameters::set_RunAs(int32)
0x1e8e  ret
```
