# __scrt_dllmain_crt_thread_detach

- ea: `0x180002db4`
- end: `0x180002dc9`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002940`

## callees

- `0x1800038b4`

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
0x180002db4  sub     rsp, 28h
0x180002db8  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002dbd  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002dc2  mov     al, 1
0x180002dc4  add     rsp, 28h
0x180002dc8  retn
```
