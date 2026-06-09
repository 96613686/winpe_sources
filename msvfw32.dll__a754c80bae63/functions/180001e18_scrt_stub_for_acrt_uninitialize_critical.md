# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180001e18`
- end: `0x180001e1b`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001694`
- `0x1800016c4`
- `0x180001768`
- `0x180001784`
- `0x180001924`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180001e18  mov     al, 1
0x180001e1a  retn
```
