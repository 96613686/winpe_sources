# Microsoft.Crm.Sandbox.SandboxWorker::ResetWorkerFromColdStart

- ea: `0x35e0`
- end: `0x35ec`
- name: `Microsoft.Crm.Sandbox.SandboxWorker::ResetWorkerFromColdStart`
- size: `12`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1c40`
- `0x1ce0`

## pseudocode

```c

```

## disassembly

```asm
0x35e0  ldsflda  int32 Microsoft.Crm.Sandbox.SandboxWorker::_executeCount
0x35e5  call     int32 [mscorlib]System.Threading.Interlocked::Decrement(int32&)
0x35ea  pop
0x35eb  ret
```
