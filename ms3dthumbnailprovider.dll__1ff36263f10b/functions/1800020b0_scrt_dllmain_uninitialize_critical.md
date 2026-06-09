# __scrt_dllmain_uninitialize_critical

- ea: `0x1800020b0`
- end: `0x1800020c4`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001cd8`

## callees

- `0x1800029c0`

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
0x1800020b0  sub     rsp, 28h
0x1800020b4  xor     ecx, ecx
0x1800020b6  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800020bb  add     rsp, 28h
0x1800020bf  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
