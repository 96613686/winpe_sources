# __scrt_dllmain_uninitialize_critical

- ea: `0x1800051a4`
- end: `0x1800051b8`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004e08`

## callees

- `0x180006004`

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
0x1800051a4  sub     rsp, 28h
0x1800051a8  xor     ecx, ecx
0x1800051aa  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800051af  add     rsp, 28h
0x1800051b3  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
