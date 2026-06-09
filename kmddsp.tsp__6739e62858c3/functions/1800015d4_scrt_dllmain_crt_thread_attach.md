# __scrt_dllmain_crt_thread_attach

- ea: `0x1800015d4`
- end: `0x1800015fc`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001090`

## callees

- `0x1800015d4`
- `0x180001c8c`

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
0x1800015d4  sub     rsp, 28h
0x1800015d8  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800015dd  test    al, al
0x1800015df  jnz     short loc_1800015E5
0x1800015e1  xor     al, al
0x1800015e3  jmp     short loc_1800015F7
0x1800015e5  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800015ea  test    al, al
0x1800015ec  jnz     short loc_1800015F5
0x1800015ee  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800015f3  jmp     short loc_1800015E1
0x1800015f5  mov     al, 1
0x1800015f7  add     rsp, 28h
0x1800015fb  retn
```
