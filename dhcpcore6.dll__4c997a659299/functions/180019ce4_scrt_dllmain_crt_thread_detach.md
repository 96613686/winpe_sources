# __scrt_dllmain_crt_thread_detach

- ea: `0x180019ce4`
- end: `0x180019cf9`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180019760`

## callees

- `0x18001b024`

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
0x180019ce4  sub     rsp, 28h
0x180019ce8  call    __scrt_stub_for_acrt_uninitialize_critical
0x180019ced  call    __scrt_stub_for_acrt_uninitialize_critical
0x180019cf2  mov     al, 1
0x180019cf4  add     rsp, 28h
0x180019cf8  retn
```
