# __scrt_dllmain_uninitialize_critical

- ea: `0x18000b594`
- end: `0x18000b5a8`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000b1e8`

## callees

- `0x18000c350`

## pseudocode

```c
__int64 _scrt_dllmain_uninitialize_critical()
{
  __int64 v0; // rcx

  _scrt_stub_for_acrt_uninitialize_critical(0);
  return _scrt_stub_for_acrt_uninitialize_critical(v0);
}

```

## disassembly

```asm
0x18000b594  sub     rsp, 28h
0x18000b598  xor     ecx, ecx
0x18000b59a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000b59f  add     rsp, 28h
0x18000b5a3  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
