# __scrt_dllmain_crt_thread_attach

- ea: `0x1800050d0`
- end: `0x1800050f8`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180004cb0`

## callees

- `0x1800050d0`
- `0x180006004`

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
0x1800050d0  sub     rsp, 28h
0x1800050d4  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800050d9  test    al, al
0x1800050db  jnz     short loc_1800050E1
0x1800050dd  xor     al, al
0x1800050df  jmp     short loc_1800050F3
0x1800050e1  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800050e6  test    al, al
0x1800050e8  jnz     short loc_1800050F1
0x1800050ea  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800050ef  jmp     short loc_1800050DD
0x1800050f1  mov     al, 1
0x1800050f3  add     rsp, 28h
0x1800050f7  retn
```
