# Microsoft.Crm.Sandbox.SandboxWorkerDrawbridgeProcess::get_WorkerPath

- ea: `0x5a60`
- end: `0x5a74`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerDrawbridgeProcess::get_WorkerPath`
- size: `20`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x5a80`
- `0x5bb0`
- `0x5c60`

## callees

- `0x9720`

## pseudocode

```c

```

## disassembly

```asm
0x5a60  ldarg.0
0x5a61  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerId()
0x5a66  stloc.0
0x5a67  ldloca.s 0
0x5a69  ldstr    aB// "B"
0x5a6e  call     instance string [mscorlib]System.Guid::ToString(string)
0x5a73  ret
```
