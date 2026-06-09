# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180002b00`
- end: `0x180002b03`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180002010`
- `0x180002040`
- `0x1800020e4`
- `0x180002100`
- `0x1800022a0`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180002b00  mov     al, 1
0x180002b02  retn
```
