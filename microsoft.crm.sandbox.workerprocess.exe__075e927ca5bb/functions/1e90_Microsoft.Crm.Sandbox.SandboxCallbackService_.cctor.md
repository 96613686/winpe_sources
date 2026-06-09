# Microsoft.Crm.Sandbox.SandboxCallbackService::.cctor

- ea: `0x1e90`
- end: `0x1eb4`
- name: `Microsoft.Crm.Sandbox.SandboxCallbackService::.cctor`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1e90  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExceptionConverter::.ctor()
0x1e95  stsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExceptionConverter Microsoft.Crm.Sandbox.SandboxCallbackService::exceptionConverter
0x1e9a  ldsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExceptionConverter Microsoft.Crm.Sandbox.SandboxCallbackService::exceptionConverter
0x1e9f  ldtoken  [mscorlib]System.TimeoutException
0x1ea4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ea9  ldc.i4   0x80044173
0x1eae  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter::AddConversion(class [mscorlib]System.Type, int32)
0x1eb3  ret
```
