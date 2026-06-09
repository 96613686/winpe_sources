# __scrt_dllmain_crt_thread_detach

- ea: `0x18000270c`
- end: `0x180002721`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800022b0`

## callees

- `0x180003050`

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
0x18000270c  sub     rsp, 28h
0x180002710  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002715  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000271a  mov     al, 1
0x18000271c  add     rsp, 28h
0x180002720  retn
```
