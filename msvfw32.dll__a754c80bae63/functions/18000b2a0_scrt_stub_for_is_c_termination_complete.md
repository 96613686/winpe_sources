# __scrt_stub_for_is_c_termination_complete

- ea: `0x18000b2a0`
- end: `0x18000b2a3`
- name: `__scrt_stub_for_is_c_termination_complete`
- size: `3`
- prototype: `BOOL __stdcall(HDRAWDIB hdd, LPDRAWDIBTIME lpddtime)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001730`

## pseudocode

```c
BOOL __stdcall _scrt_stub_for_is_c_termination_complete(HDRAWDIB hdd, LPDRAWDIBTIME lpddtime)
{
  return 0;
}

```

## disassembly

```asm
0x18000b2a0  xor     eax, eax
0x18000b2a2  retn
```
