# __scrt_dllmain_uninitialize_critical

- ea: `0x1800028c0`
- end: `0x1800028d4`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800024a0`

## callees

- `0x1800034e0`

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
0x1800028c0  sub     rsp, 28h
0x1800028c4  xor     ecx, ecx
0x1800028c6  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800028cb  add     rsp, 28h
0x1800028cf  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
