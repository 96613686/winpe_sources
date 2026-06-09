# Microsoft.Crm.Sandbox.SandboxCallbackService::DiscardClient

- ea: `0x21f0`
- end: `0x2219`
- name: `Microsoft.Crm.Sandbox.SandboxCallbackService::DiscardClient`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2030`

## callees

- `0x22d0`

## string_xrefs

- `0x21fd`: `SandboxCallbackService.DiscardClient`

## pseudocode

```c

```

## disassembly

```asm
0x21f0  ldarg.0
0x21f1  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxCallbackService::get_Context()
0x21f6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x21fb  ldc.i4.s 0x21
0x21fd  ldstr    aSandboxcallbac_7// "SandboxCallbackService.DiscardClient"
0x2202  ldc.i4.0
0x2203  newarr   [mscorlib]System.Object
0x2208  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x220d  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<var<u1>> class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<class Microsoft.Crm.Sandbox.SandboxSdkClient>::get_Instance()
0x2212  ldarg.1
0x2213  callvirt instance void class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<class Microsoft.Crm.Sandbox.SandboxSdkClient>::DiscardClient(var<u1>)
0x2218  ret
```
