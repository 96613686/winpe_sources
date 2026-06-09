# Microsoft.Crm.Workflow.WorkflowContext::SavePendingWorkflowInstanceState

- ea: `0x1ac0`
- end: `0x1c62`
- name: `Microsoft.Crm.Workflow.WorkflowContext::SavePendingWorkflowInstanceState`
- size: `418`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1a90`
- `0x1ac0`
- `0x2290`

## string_xrefs

- `0x1b65`: `SavePendingWorkflowInstanceState: Failed save for workflow {0}; state is {1} bytes, postpone until: {2}, blocked: {3}. Delayed update command queued`

## pseudocode

```c

```

## disassembly

```asm
0x1ac0  ldarg.0
0x1ac1  ldfld    object [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_lockObject
0x1ac6  stloc.0
0x1ac7  ldc.i4.0
0x1ac8  stloc.1
0x1ac9  ldloc.0
0x1aca  ldloca.s 1
0x1acc  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x1ad1  ldarg.0
0x1ad2  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_instanceState
0x1ad7  callvirt instance bool [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase::get_IsEmpty()
0x1adc  brtrue   loc_1BE6
0x1ae1  ldarg.0
0x1ae2  ldfld    valuetype [mscorlib]System.DateTime [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_nextStateUpdate
0x1ae7  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x1aec  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1af1  ldarg.2
0x1af2  or
0x1af3  brfalse  loc_1BE6
0x1af8  ldarg.0
0x1af9  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Workflow.WorkflowContext::get_OrganizationConfiguration()
0x1afe  newobj   instance void Microsoft.Crm.Workflow.WorkflowDataAccess::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration config)
0x1b03  stloc.2
0x1b04  ldarg.0
0x1b05  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_instanceState
0x1b0a  callvirt instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase::IncrementInstanceSaveCounter()
0x1b0f  ldloc.2
0x1b10  ldarg.1
0x1b11  ldarg.0
0x1b12  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_instanceState
0x1b17  callvirt instance string [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase::get_WorkflowState()
0x1b1c  ldarg.0
0x1b1d  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_instanceState
0x1b22  callvirt instance bool [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase::get_IsBlocked()
0x1b27  ldarg.0
0x1b28  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_instanceState
0x1b2d  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase::get_PostponeUntil()
0x1b32  callvirt instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IWorkflowDataAccess::SaveWorkflowInstanceState(valuetype [mscorlib]System.Guid, string, bool, valuetype [mscorlib]System.DateTime)
0x1b37  ldarg.0
0x1b38  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::get_InstanceState()
0x1b3d  ldc.i4.0
0x1b3e  callvirt instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase::set_WorkflowStateUpdated(bool)
0x1b43  leave    loc_1BCE
0x1b48  ldarg.2
0x1b49  brfalse.s loc_1B5D
0x1b4b  ldarg.0
0x1b4c  callvirt instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::EnqueueStateSaveCommand()
0x1b51  ldarg.0
0x1b52  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::get_InstanceState()
0x1b57  ldc.i4.0
0x1b58  callvirt instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase::set_WorkflowStateUpdated(bool)
0x1b5d  ldarg.0
0x1b5e  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::get_OrganizationId()
0x1b63  ldc.i4.s 0x1E
0x1b65  ldstr    aSavependingwor// "SavePendingWorkflowInstanceState: Faile"...
0x1b6a  ldc.i4.4
0x1b6b  newarr   [mscorlib]System.Object
0x1b70  dup
0x1b71  ldc.i4.0
0x1b72  ldarg.1
0x1b73  box      [mscorlib]System.Guid
0x1b78  stelem.ref
0x1b79  dup
0x1b7a  ldc.i4.1
0x1b7b  ldarg.0
0x1b7c  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_instanceState
0x1b81  callvirt instance bool [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase::get_IsEmpty()
0x1b86  brtrue.s loc_1B9A
0x1b88  ldarg.0
0x1b89  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_instanceState
0x1b8e  callvirt instance string [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase::get_WorkflowState()
0x1b93  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1b98  br.s     loc_1B9B
0x1b9a  ldc.i4.0
0x1b9b  box      [mscorlib]System.Int32
0x1ba0  stelem.ref
0x1ba1  dup
0x1ba2  ldc.i4.2
0x1ba3  ldarg.0
0x1ba4  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_instanceState
0x1ba9  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase::get_PostponeUntil()
0x1bae  box      [mscorlib]System.DateTime
0x1bb3  stelem.ref
0x1bb4  dup
0x1bb5  ldc.i4.3
0x1bb6  ldarg.0
0x1bb7  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_instanceState
0x1bbc  callvirt instance bool [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase::get_IsBlocked()
0x1bc1  box      [mscorlib]System.Boolean
0x1bc6  stelem.ref
0x1bc7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1bcc  rethrow
0x1bce  ldarg.0
0x1bcf  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MaxValue
0x1bd4  stfld    valuetype [mscorlib]System.DateTime [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_nextStateUpdate
0x1bd9  ldarg.0
0x1bda  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_instanceState
0x1bdf  callvirt instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase::Clear()
0x1be4  leave.s  loc_1C61
0x1be6  ldarg.0
0x1be7  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::get_OrganizationId()
0x1bec  ldc.i4.s 0x1E
0x1bee  ldstr    aSavependingwor_0// "SavePendingWorkflowInstanceState: Skipp"...
0x1bf3  ldc.i4.4
0x1bf4  newarr   [mscorlib]System.Object
0x1bf9  dup
0x1bfa  ldc.i4.0
0x1bfb  ldarg.1
0x1bfc  box      [mscorlib]System.Guid
0x1c01  stelem.ref
0x1c02  dup
0x1c03  ldc.i4.1
0x1c04  ldarg.0
0x1c05  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_instanceState
0x1c0a  callvirt instance bool [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase::get_IsEmpty()
0x1c0f  brtrue.s loc_1C23
0x1c11  ldarg.0
0x1c12  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_instanceState
0x1c17  callvirt instance string [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase::get_WorkflowState()
0x1c1c  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1c21  br.s     loc_1C24
0x1c23  ldc.i4.0
0x1c24  box      [mscorlib]System.Int32
0x1c29  stelem.ref
0x1c2a  dup
0x1c2b  ldc.i4.2
0x1c2c  ldarg.0
0x1c2d  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_instanceState
0x1c32  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase::get_PostponeUntil()
0x1c37  box      [mscorlib]System.DateTime
0x1c3c  stelem.ref
0x1c3d  dup
0x1c3e  ldc.i4.3
0x1c3f  ldarg.0
0x1c40  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowContextBase::_instanceState
0x1c45  callvirt instance bool [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowInstanceStateBase::get_IsBlocked()
0x1c4a  box      [mscorlib]System.Boolean
0x1c4f  stelem.ref
0x1c50  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1c55  leave.s  loc_1C61
0x1c57  ldloc.1
0x1c58  brfalse.s loc_1C60
0x1c5a  ldloc.0
0x1c5b  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x1c60  endfinally
0x1c61  ret
```
