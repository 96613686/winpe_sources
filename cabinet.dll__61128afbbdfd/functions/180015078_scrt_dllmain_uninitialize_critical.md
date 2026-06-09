# __scrt_dllmain_uninitialize_critical

- ea: `0x180015078`
- end: `0x18001508c`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180014ba8`

## callees

- `0x1800156d4`

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
0x180015078  sub     rsp, 28h
0x18001507c  xor     ecx, ecx
0x18001507e  call    __scrt_stub_for_acrt_uninitialize_critical
0x180015083  add     rsp, 28h
0x180015087  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
