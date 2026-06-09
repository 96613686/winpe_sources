# __scrt_dllmain_uninitialize_critical

- ea: `0x18000fb94`
- end: `0x18000fba8`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000f7f8`

## callees

- `0x180010860`

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
0x18000fb94  sub     rsp, 28h
0x18000fb98  xor     ecx, ecx
0x18000fb9a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000fb9f  add     rsp, 28h
0x18000fba3  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
