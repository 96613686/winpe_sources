# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180002218`
- end: `0x18000221b`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001628`
- `0x180001658`
- `0x1800016fc`
- `0x180001718`
- `0x1800018b8`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180002218  mov     al, 1
0x18000221a  retn
```
