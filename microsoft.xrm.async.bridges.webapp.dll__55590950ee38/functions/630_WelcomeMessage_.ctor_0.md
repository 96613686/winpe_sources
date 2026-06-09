# WelcomeMessage::.ctor_0

- ea: `0x630`
- end: `0x649`
- name: `WelcomeMessage::.ctor_0`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x620`

## callees

- `0x650`

## pseudocode

```c

```

## disassembly

```asm
0x630  ldarg.0
0x631  ldarg.1
0x632  callvirt instance string [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.VersionInfo::get_Title()
0x637  ldarg.1
0x638  callvirt instance string [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.VersionInfo::get_Version()
0x63d  ldarg.1
0x63e  callvirt instance string [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.VersionInfo::get_Revision()
0x643  call     instance void WelcomeMessage::.ctor(string title, string version, string revision)
0x648  ret
```
