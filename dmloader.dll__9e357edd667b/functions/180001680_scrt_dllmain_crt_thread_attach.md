# __scrt_dllmain_crt_thread_attach

- ea: `0x180001680`
- end: `0x1800016a8`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001260`

## callees

- `0x180001680`
- `0x180001f50`

## pseudocode

```c
char _scrt_dllmain_crt_thread_attach()
{
  if ( !(unsigned __int8)_scrt_stub_for_acrt_uninitialize_critical() )
    return 0;
  if ( !(unsigned __int8)_scrt_stub_for_acrt_uninitialize_critical() )
  {
    _scrt_stub_for_acrt_uninitialize_critical();
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180001680  sub     rsp, 28h
0x180001684  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001689  test    al, al
0x18000168b  jnz     short loc_180001691
0x18000168d  xor     al, al
0x18000168f  jmp     short loc_1800016A3
0x180001691  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001696  test    al, al
0x180001698  jnz     short loc_1800016A1
0x18000169a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000169f  jmp     short loc_18000168D
0x1800016a1  mov     al, 1
0x1800016a3  add     rsp, 28h
0x1800016a7  retn
```
