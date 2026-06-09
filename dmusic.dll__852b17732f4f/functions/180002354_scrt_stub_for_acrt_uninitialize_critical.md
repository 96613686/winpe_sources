# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180002354`
- end: `0x180002357`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001780`
- `0x1800017b0`
- `0x180001854`
- `0x180001870`
- `0x180001a10`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180002354  mov     al, 1
0x180002356  retn
```
