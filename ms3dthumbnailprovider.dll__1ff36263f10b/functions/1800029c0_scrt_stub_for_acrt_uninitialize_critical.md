# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x1800029c0`
- end: `0x1800029c3`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001fdc`
- `0x18000200c`
- `0x1800020b0`
- `0x1800020cc`
- `0x18000226c`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x1800029c0  mov     al, 1
0x1800029c2  retn
```
