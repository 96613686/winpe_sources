# __scrt_dllmain_crt_thread_detach

- ea: `0x180001768`
- end: `0x18000177d`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001210`

## callees

- `0x180001ebc`

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
0x180001768  sub     rsp, 28h
0x18000176c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001771  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001776  mov     al, 1
0x180001778  add     rsp, 28h
0x18000177c  retn
```
