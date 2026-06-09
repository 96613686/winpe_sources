# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180005640`
- end: `0x180005643`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180004df8`
- `0x180004e28`
- `0x180004ecc`
- `0x180004ee8`
- `0x180005088`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180005640  mov     al, 1
0x180005642  retn
```
