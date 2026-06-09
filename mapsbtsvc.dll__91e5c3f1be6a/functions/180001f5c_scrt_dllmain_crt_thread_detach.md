# __scrt_dllmain_crt_thread_detach

- ea: `0x180001f5c`
- end: `0x180001f71`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001af0`

## callees

- `0x1800029b4`

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
0x180001f5c  sub     rsp, 28h
0x180001f60  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001f65  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001f6a  mov     al, 1
0x180001f6c  add     rsp, 28h
0x180001f70  retn
```
