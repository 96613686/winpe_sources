# __scrt_dllmain_crt_thread_detach

- ea: `0x18000faf0`
- end: `0x18000fb05`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000f6a0`

## callees

- `0x180010860`

## pseudocode

```c
char _scrt_dllmain_crt_thread_detach()
{
  _scrt_stub_for_acrt_uninitialize_critical();
  _scrt_stub_for_acrt_uninitialize_critical();
  return 1;
}

```

## disassembly

```asm
0x18000faf0  sub     rsp, 28h
0x18000faf4  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000faf9  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000fafe  mov     al, 1
0x18000fb00  add     rsp, 28h
0x18000fb04  retn
```
