# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180001d30`
- end: `0x180001d33`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001644`
- `0x180001674`
- `0x180001718`
- `0x180001734`
- `0x1800018d4`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180001d30  mov     al, 1
0x180001d32  retn
```
