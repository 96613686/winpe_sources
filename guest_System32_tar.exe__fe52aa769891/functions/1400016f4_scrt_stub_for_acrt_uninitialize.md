# __scrt_stub_for_acrt_uninitialize

- ea: `0x1400016f4`
- end: `0x1400016f7`
- name: `__scrt_stub_for_acrt_uninitialize`
- size: `3`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140001090`
- `0x1400013d0`
- `0x140001570`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize()
{
  return 1;
}

```

## disassembly

```asm
0x1400016f4  mov     al, 1
0x1400016f6  retn
```
