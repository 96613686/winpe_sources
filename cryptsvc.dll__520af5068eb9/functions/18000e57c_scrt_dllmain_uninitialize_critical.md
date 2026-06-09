# __scrt_dllmain_uninitialize_critical

- ea: `0x18000e57c`
- end: `0x18000e590`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000e0d8`

## callees

- `0x18000f190`

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
0x18000e57c  sub     rsp, 28h
0x18000e580  xor     ecx, ecx
0x18000e582  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000e587  add     rsp, 28h
0x18000e58b  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
