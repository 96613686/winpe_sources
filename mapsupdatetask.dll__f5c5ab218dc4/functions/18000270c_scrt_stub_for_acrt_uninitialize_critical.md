# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x18000270c`
- end: `0x18000270f`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001cd4`
- `0x180001d04`
- `0x180001da8`
- `0x180001dc4`
- `0x180001f64`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x18000270c  mov     al, 1
0x18000270e  retn
```
