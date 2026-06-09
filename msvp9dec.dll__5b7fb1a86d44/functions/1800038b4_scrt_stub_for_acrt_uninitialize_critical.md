# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x1800038b4`
- end: `0x1800038b7`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180002d84`
- `0x180002db4`
- `0x180002e58`
- `0x180002e74`
- `0x180003014`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x1800038b4  mov     al, 1
0x1800038b6  retn
```
