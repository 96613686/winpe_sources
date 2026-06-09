# __scrt_dllmain_uninitialize_critical

- ea: `0x18000e9a8`
- end: `0x18000e9bc`
- name: `__scrt_dllmain_uninitialize_critical`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000e528`

## callees

- `0x18000f028`

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
0x18000e9a8  sub     rsp, 28h
0x18000e9ac  xor     ecx, ecx
0x18000e9ae  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000e9b3  add     rsp, 28h
0x18000e9b7  jmp     __scrt_stub_for_acrt_uninitialize_critical
```
