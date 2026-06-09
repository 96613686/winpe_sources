# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180001f50`
- end: `0x180001f53`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001680`
- `0x1800016b0`
- `0x180001754`
- `0x180001770`
- `0x180001910`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180001f50  mov     al, 1
0x180001f52  retn
```
