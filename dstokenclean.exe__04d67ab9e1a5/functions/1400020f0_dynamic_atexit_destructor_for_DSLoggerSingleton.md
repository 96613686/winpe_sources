# _dynamic_atexit_destructor_for__DSLoggerSingleton__

- ea: `0x1400020f0`
- end: `0x1400020fc`
- name: `_dynamic_atexit_destructor_for__DSLoggerSingleton__`
- size: `12`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140001aa0`

## pseudocode

```c
int dynamic_atexit_destructor_for__DSLoggerSingleton__()
{
  return tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>::~static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>(&DSLoggerSingleton);
}

```

## disassembly

```asm
0x1400020f0  lea     rcx, ?DSLoggerSingleton@@3V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@tlx@@A; lpInitOnce
0x1400020f7  jmp     ??1?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@tlx@@QEAA@XZ; tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>::~static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>(void)
```
