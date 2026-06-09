# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180002604`
- end: `0x180002607`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001c58`
- `0x180001c88`
- `0x180001d2c`
- `0x180001d48`
- `0x180001ee8`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180002604  mov     al, 1
0x180002606  retn
```
