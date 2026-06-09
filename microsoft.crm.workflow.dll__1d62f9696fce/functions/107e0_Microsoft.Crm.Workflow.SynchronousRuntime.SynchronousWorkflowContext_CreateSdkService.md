# Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext::CreateSdkService

- ea: `0x107e0`
- end: `0x10822`
- name: `Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext::CreateSdkService`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x73d0`
- `0x7450`
- `0x7460`
- `0x107e0`
- `0x10950`

## string_xrefs

- `0x107e8`: `Delete`

## pseudocode

```c

```

## disassembly

```asm
0x107e0  ldarg.0
0x107e1  call     instance string Microsoft.Crm.Workflow.WorkflowContextBase::get_MessageName()
0x107e6  stloc.0
0x107e7  ldloc.0
0x107e8  ldstr    aDelete// "Delete"
0x107ed  call     bool [mscorlib]System.String::op_Equality(string, string)
0x107f2  brfalse.s loc_1080B
0x107f4  ldarg.0
0x107f5  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext::get_OrgServiceFactory()
0x107fa  ldarg.0
0x107fb  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.WorkflowContextBase::get_InitiatingUserId()
0x10800  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x10805  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory::CreateOrganizationService(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0x1080a  ret
0x1080b  ldarg.0
0x1080c  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext::get_OrgServiceFactory()
0x10811  ldarg.0
0x10812  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.WorkflowContextBase::get_UserId()
0x10817  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x1081c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory::CreateOrganizationService(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0x10821  ret
```
