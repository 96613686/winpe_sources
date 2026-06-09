# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180001ddc`
- end: `0x180001ddf`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001620`
- `0x180001650`
- `0x1800016f4`
- `0x180001710`
- `0x1800018b0`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180001ddc  mov     al, 1
0x180001dde  retn
```
