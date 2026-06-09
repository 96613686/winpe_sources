# __scrt_dllmain_crt_thread_detach

- ea: `0x180001820`
- end: `0x180001835`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001240`

## callees

- `0x18000208c`

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
0x180001820  sub     rsp, 28h
0x180001824  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001829  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000182e  mov     al, 1
0x180001830  add     rsp, 28h
0x180001834  retn
```
