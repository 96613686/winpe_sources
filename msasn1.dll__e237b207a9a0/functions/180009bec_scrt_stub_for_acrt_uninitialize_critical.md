# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180009bec`
- end: `0x180009bef`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800094c8`
- `0x1800094f8`
- `0x18000959c`
- `0x1800095b8`
- `0x180009758`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180009bec  mov     al, 1
0x180009bee  retn
```
