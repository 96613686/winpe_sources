# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x18000299c`
- end: `0x18000299f`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001240`
- `0x180001270`
- `0x180001314`
- `0x180001330`
- `0x1800014d0`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x18000299c  mov     al, 1
0x18000299e  retn
```
