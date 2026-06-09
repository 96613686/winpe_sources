# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x1800029cc`
- end: `0x1800029cf`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001dbc`
- `0x180001dec`
- `0x180001e90`
- `0x180001eac`
- `0x18000204c`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x1800029cc  mov     al, 1
0x1800029ce  retn
```
