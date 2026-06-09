# Microsoft.Crm.Sandbox.SandboxCallTracker::Dispose_0

- ea: `0x4b0`
- end: `0x4c4`
- name: `Microsoft.Crm.Sandbox.SandboxCallTracker::Dispose_0`
- size: `20`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x4a0`
- `0x4d0`

## callees

- `0xc0`
- `0x190`
- `0x480`
- `0x4b0`

## pseudocode

```c

```

## disassembly

```asm
0x4b0  ldarg.1
0x4b1  brfalse.s loc_4C3
0x4b3  call     class Microsoft.Crm.Sandbox.SandboxCallManager Microsoft.Crm.Sandbox.SandboxCallManager::get_Instance()
0x4b8  ldarg.0
0x4b9  call     instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo Microsoft.Crm.Sandbox.SandboxCallTracker::get_CallInfo()
0x4be  callvirt instance void Microsoft.Crm.Sandbox.SandboxCallManager::RemoveCallTracker(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo sandboxCallInfo)
0x4c3  ret
```
