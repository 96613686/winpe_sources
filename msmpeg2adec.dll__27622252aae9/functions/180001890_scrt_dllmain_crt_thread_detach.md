# __scrt_dllmain_crt_thread_detach

- ea: `0x180001890`
- end: `0x1800018a5`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001440`

## callees

- `0x180009658`

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
0x180001890  sub     rsp, 28h
0x180001894  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001899  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000189e  mov     al, 1
0x1800018a0  add     rsp, 28h
0x1800018a4  retn
```
