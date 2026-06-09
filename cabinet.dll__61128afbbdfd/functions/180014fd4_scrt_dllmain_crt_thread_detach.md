# __scrt_dllmain_crt_thread_detach

- ea: `0x180014fd4`
- end: `0x180014fe9`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180014a50`

## callees

- `0x1800156d4`

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
0x180014fd4  sub     rsp, 28h
0x180014fd8  call    __scrt_stub_for_acrt_uninitialize_critical
0x180014fdd  call    __scrt_stub_for_acrt_uninitialize_critical
0x180014fe2  mov     al, 1
0x180014fe4  add     rsp, 28h
0x180014fe8  retn
```
