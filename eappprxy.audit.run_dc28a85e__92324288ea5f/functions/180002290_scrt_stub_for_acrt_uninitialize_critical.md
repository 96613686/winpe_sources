# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180002290`
- end: `0x180002293`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001868`
- `0x180001898`
- `0x18000193c`
- `0x180001958`
- `0x180001af8`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180002290  mov     al, 1
0x180002292  retn
```
