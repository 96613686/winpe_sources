# __scrt_dllmain_crt_thread_detach

- ea: `0x180020460`
- end: `0x180020475`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001fee0`

## callees

- `0x18002134c`

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
0x180020460  sub     rsp, 28h
0x180020464  call    __scrt_stub_for_acrt_uninitialize_critical
0x180020469  call    __scrt_stub_for_acrt_uninitialize_critical
0x18002046e  mov     al, 1
0x180020470  add     rsp, 28h
0x180020474  retn
```
