# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180001c8c`
- end: `0x180001c8f`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800015d4`
- `0x180001604`
- `0x1800016a8`
- `0x1800016c4`
- `0x180001864`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180001c8c  mov     al, 1
0x180001c8e  retn
```
