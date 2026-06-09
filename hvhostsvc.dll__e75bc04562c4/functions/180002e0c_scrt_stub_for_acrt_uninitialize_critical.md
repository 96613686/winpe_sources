# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180002e0c`
- end: `0x180002e0f`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800021b0`
- `0x1800021e0`
- `0x180002284`
- `0x1800022a0`
- `0x180002440`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180002e0c  mov     al, 1
0x180002e0e  retn
```
