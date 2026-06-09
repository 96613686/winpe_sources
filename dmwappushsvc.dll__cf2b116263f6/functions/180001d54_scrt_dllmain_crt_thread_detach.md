# __scrt_dllmain_crt_thread_detach

- ea: `0x180001d54`
- end: `0x180001d69`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800016f0`

## callees

- `0x1800027f4`

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
0x180001d54  sub     rsp, 28h
0x180001d58  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001d5d  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001d62  mov     al, 1
0x180001d64  add     rsp, 28h
0x180001d68  retn
```
