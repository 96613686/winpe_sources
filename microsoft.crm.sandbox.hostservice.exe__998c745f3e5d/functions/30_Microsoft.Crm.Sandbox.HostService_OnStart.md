# Microsoft.Crm.Sandbox.HostService::OnStart

- ea: `0x30`
- end: `0x64`
- name: `Microsoft.Crm.Sandbox.HostService::OnStart`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140`

## string_xrefs

- `0x37`: `HostService.OnStart: enter`
- `0x53`: `HostService.OnStart: exit`

## pseudocode

```c

```

## disassembly

```asm
0x30  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x35  ldc.i4.s 0x26
0x37  ldstr    aHostserviceOns// "HostService.OnStart: enter"
0x3c  ldc.i4.0
0x3d  newarr   [mscorlib]System.Object
0x42  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x47  call     void Microsoft.Crm.Sandbox.HostService::InitializeThreadProc()
0x4c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x51  ldc.i4.s 0x26
0x53  ldstr    aHostserviceOns_0// "HostService.OnStart: exit"
0x58  ldc.i4.0
0x59  newarr   [mscorlib]System.Object
0x5e  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x63  ret
```
