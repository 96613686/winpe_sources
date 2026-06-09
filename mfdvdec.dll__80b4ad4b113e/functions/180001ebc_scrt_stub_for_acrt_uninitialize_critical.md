# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180001ebc`
- end: `0x180001ebf`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001738`
- `0x180001768`
- `0x18000180c`
- `0x180001828`
- `0x1800019c8`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180001ebc  mov     al, 1
0x180001ebe  retn
```
