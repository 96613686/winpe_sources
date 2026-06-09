# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180006004`
- end: `0x180006007`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800050d0`
- `0x180005100`
- `0x1800051a4`
- `0x1800051c0`
- `0x180005360`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180006004  mov     al, 1
0x180006006  retn
```
