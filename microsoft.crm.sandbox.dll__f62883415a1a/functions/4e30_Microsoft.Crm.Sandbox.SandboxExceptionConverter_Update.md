# Microsoft.Crm.Sandbox.SandboxExceptionConverter::Update

- ea: `0x4e30`
- end: `0x4e50`
- name: `Microsoft.Crm.Sandbox.SandboxExceptionConverter::Update`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x4e30`
- `0x80a0`

## pseudocode

```c

```

## disassembly

```asm
0x4e30  ldarg.1
0x4e31  brtrue.s loc_4E34
0x4e33  ret
0x4e34  ldarg.1
0x4e35  ldc.i4.6
0x4e36  callvirt instance int32 Microsoft.Crm.Sandbox.SandboxWorkerConfiguration::get_Item(valuetype Microsoft.Crm.Sandbox.SandboxWorkerProperty key)
0x4e3b  stsfld   int32 Microsoft.Crm.Sandbox.SandboxExceptionConverter::_nestingDepth
0x4e40  ldarg.1
0x4e41  ldc.i4.7
0x4e42  callvirt instance int32 Microsoft.Crm.Sandbox.SandboxWorkerConfiguration::get_Item(valuetype Microsoft.Crm.Sandbox.SandboxWorkerProperty key)
0x4e47  ldc.i4.0
0x4e48  cgt
0x4e4a  stsfld   bool Microsoft.Crm.Sandbox.SandboxExceptionConverter::_includeCallStack
0x4e4f  ret
```
