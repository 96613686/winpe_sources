# Microsoft.Crm.Sandbox.SandboxWorkerMain::get_SandboxFilesPath

- ea: `0x3a80`
- end: `0x3a98`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerMain::get_SandboxFilesPath`
- size: `24`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xfa0`
- `0x1b30`
- `0x3820`

## callees

- `0x3a80`

## string_xrefs

- `0x3a87`: `SandboxWorkerMain.SandboxFilesPath: The sandbox files path is not set`

## pseudocode

```c

```

## disassembly

```asm
0x3a80  ldsfld   string Microsoft.Crm.Sandbox.SandboxWorkerMain::_sandboxFilesPath
0x3a85  brtrue.s loc_3A92
0x3a87  ldstr    aSandboxworkerm_0// "SandboxWorkerMain.SandboxFilesPath: The"...
0x3a8c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x3a91  throw
0x3a92  ldsfld   string Microsoft.Crm.Sandbox.SandboxWorkerMain::_sandboxFilesPath
0x3a97  ret
```
