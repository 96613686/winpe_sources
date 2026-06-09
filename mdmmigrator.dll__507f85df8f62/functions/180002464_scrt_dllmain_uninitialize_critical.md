# __scrt_dllmain_uninitialize_critical

- ea: `0x180002464`
- end: `0x180002478`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800020c8`

## callees

- `0x1800038cc`

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
0x180002464  sub     rsp, 28h
0x180002468  xor     ecx, ecx
0x18000246a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000246f  add     rsp, 28h
0x180002473  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
