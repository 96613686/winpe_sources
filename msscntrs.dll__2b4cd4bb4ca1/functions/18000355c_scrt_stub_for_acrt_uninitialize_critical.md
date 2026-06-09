# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x18000355c`
- end: `0x18000355f`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180002664`
- `0x180002694`
- `0x180002738`
- `0x180002754`
- `0x1800028f4`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x18000355c  mov     al, 1
0x18000355e  retn
```
