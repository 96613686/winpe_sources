# Microsoft.Crm.Sandbox.SandboxCallbackService::GetDefaultSandboxClientInstance

- ea: `0x2220`
- end: `0x2237`
- name: `Microsoft.Crm.Sandbox.SandboxCallbackService::GetDefaultSandboxClientInstance`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x2bb0`
- `0x2d10`

## pseudocode

```c

```

## disassembly

```asm
0x2220  newobj   instance void Microsoft.Crm.Sandbox.SandboxSdkClient::.ctor()
0x2225  dup
0x2226  ldarg.0
0x2227  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo Microsoft.Crm.Sandbox.SandboxCallbackService::callInfo
0x222c  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ParentCallInfo()
0x2231  callvirt instance void Microsoft.Crm.Sandbox.SandboxSdkClient::Start(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo callInfo)
0x2236  ret
```
