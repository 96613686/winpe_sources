# __scrt_dllmain_crt_thread_detach

- ea: `0x1800016c4`
- end: `0x1800016d9`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001140`

## callees

- `0x180001e18`

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
0x1800016c4  sub     rsp, 28h
0x1800016c8  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016cd  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016d2  mov     al, 1
0x1800016d4  add     rsp, 28h
0x1800016d8  retn
```
