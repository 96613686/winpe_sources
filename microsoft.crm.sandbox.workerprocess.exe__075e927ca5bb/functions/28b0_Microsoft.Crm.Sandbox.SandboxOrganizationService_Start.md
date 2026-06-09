# Microsoft.Crm.Sandbox.SandboxOrganizationService::Start

- ea: `0x28b0`
- end: `0x28d7`
- name: `Microsoft.Crm.Sandbox.SandboxOrganizationService::Start`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3aa0`

## callees

- `0x39f0`

## string_xrefs

- `0x28b7`: `SandboxOrganizationService.Start`

## pseudocode

```c

```

## disassembly

```asm
0x28b0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x28b5  ldc.i4.s 0x26
0x28b7  ldstr    aSandboxorganiz_14// "SandboxOrganizationService.Start"
0x28bc  ldc.i4.0
0x28bd  newarr   [mscorlib]System.Object
0x28c2  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x28c7  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<var<u1>> class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<class Microsoft.Crm.Sandbox.SandboxSdkClient>::get_Instance()
0x28cc  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerConfiguration Microsoft.Crm.Sandbox.SandboxWorker::get_WorkerConfiguration()
0x28d1  callvirt instance void class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<class Microsoft.Crm.Sandbox.SandboxSdkClient>::set_WorkerConfiguration(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerConfiguration)
0x28d6  ret
```
