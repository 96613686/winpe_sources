# __scrt_dllmain_crt_thread_detach

- ea: `0x180005100`
- end: `0x180005115`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180004cb0`

## callees

- `0x180006004`

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
0x180005100  sub     rsp, 28h
0x180005104  call    __scrt_stub_for_acrt_uninitialize_critical
0x180005109  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000510e  mov     al, 1
0x180005110  add     rsp, 28h
0x180005114  retn
```
