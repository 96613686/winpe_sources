# __scrt_dllmain_crt_thread_attach

- ea: `0x1800015d0`
- end: `0x1800015f8`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800011b0`

## callees

- `0x1800015d0`
- `0x18000206c`

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
0x1800015d0  sub     rsp, 28h
0x1800015d4  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800015d9  test    al, al
0x1800015db  jnz     short loc_1800015E1
0x1800015dd  xor     al, al
0x1800015df  jmp     short loc_1800015F3
0x1800015e1  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800015e6  test    al, al
0x1800015e8  jnz     short loc_1800015F1
0x1800015ea  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800015ef  jmp     short loc_1800015DD
0x1800015f1  mov     al, 1
0x1800015f3  add     rsp, 28h
0x1800015f7  retn
```
