# Microsoft.Crm.Workflow.Services.ActivityServiceBase::UpdateLog

- ea: `0x149c0`
- end: `0x14a34`
- name: `Microsoft.Crm.Workflow.Services.ActivityServiceBase::UpdateLog`
- size: `116`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x16490`
- `0x168b0`
- `0x18c00`
- `0x18d50`
- `0x19020`

## callees

- `0x6960`
- `0x6a40`
- `0x14770`
- `0x149c0`

## pseudocode

```c

```

## disassembly

```asm
0x149c0  ldarg.0
0x149c1  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x149c6  callvirt instance bool Microsoft.Crm.Workflow.ICommonWorkflowContext::get_IsLoggingEnabled()
0x149cb  brfalse.s loc_14A33
0x149cd  ldarg.0
0x149ce  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x149d3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x149d8  ldc.i4.s 0x1E
0x149da  ldstr    aUpdatingWorkfl// "Updating workflow log {0}."
0x149df  ldc.i4.1
0x149e0  newarr   [mscorlib]System.Object
0x149e5  dup
0x149e6  ldc.i4.0
0x149e7  ldarg.1
0x149e8  box      [mscorlib]System.Guid
0x149ed  stelem.ref
0x149ee  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x149f3  ldarg.0
0x149f4  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x149f9  ldarg.1
0x149fa  ldarg.2
0x149fb  ldarg.3
0x149fc  ldarg.s  4
0x149fe  callvirt instance void Microsoft.Crm.Workflow.ICommonWorkflowContext::UpdateWorkflowLog(valuetype [mscorlib]System.Guid logId, int32 errorCode, string errorMessage, int32 status)
0x14a03  leave.s  loc_14A33
0x14a05  stloc.0
0x14a06  ldloc.0
0x14a07  ldarg.0
0x14a08  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x14a0d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x14a12  ldc.i4.s 0x1E
0x14a14  ldstr    aErrorWhileUpda// "Error while updating workflow log {0}: "...
0x14a19  ldc.i4.2
0x14a1a  newarr   [mscorlib]System.Object
0x14a1f  dup
0x14a20  ldc.i4.0
0x14a21  ldarg.1
0x14a22  box      [mscorlib]System.Guid
0x14a27  stelem.ref
0x14a28  dup
0x14a29  ldc.i4.1
0x14a2a  ldloc.0
0x14a2b  stelem.ref
0x14a2c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x14a31  leave.s  loc_14A33
0x14a33  ret
```
