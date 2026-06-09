# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x1800022f0`
- end: `0x1800022f3`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800016c8`
- `0x1800016f8`
- `0x18000179c`
- `0x1800017b8`
- `0x180001958`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x1800022f0  mov     al, 1
0x1800022f2  retn
```
