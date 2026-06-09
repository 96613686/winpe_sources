# Microsoft.Crm.Sandbox.SandboxOrganizationService::Cleanup

- ea: `0x2880`
- end: `0x28a6`
- name: `Microsoft.Crm.Sandbox.SandboxOrganizationService::Cleanup`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2ac0`

## callees

- `0x22f0`

## string_xrefs

- `0x2887`: `SandboxOrganizationService.Cleanup`

## pseudocode

```c

```

## disassembly

```asm
0x2880  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2885  ldc.i4.s 0x26
0x2887  ldstr    aSandboxorganiz_13// "SandboxOrganizationService.Cleanup"
0x288c  ldc.i4.0
0x288d  newarr   [mscorlib]System.Object
0x2892  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2897  ldarg.0
0x2898  ldc.i4.1
0x2899  stfld    bool Microsoft.Crm.Sandbox.SandboxCallbackService::blocked
0x289e  ldarg.0
0x289f  ldnull
0x28a0  call     instance void Microsoft.Crm.Sandbox.SandboxCallbackService::set_Context(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext value)
0x28a5  ret
```
