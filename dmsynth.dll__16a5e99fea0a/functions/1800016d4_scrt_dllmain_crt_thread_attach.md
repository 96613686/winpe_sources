# __scrt_dllmain_crt_thread_attach

- ea: `0x1800016d4`
- end: `0x1800016fc`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001180`

## callees

- `0x1800016d4`
- `0x180001da8`

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
0x1800016d4  sub     rsp, 28h
0x1800016d8  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016dd  test    al, al
0x1800016df  jnz     short loc_1800016E5
0x1800016e1  xor     al, al
0x1800016e3  jmp     short loc_1800016F7
0x1800016e5  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016ea  test    al, al
0x1800016ec  jnz     short loc_1800016F5
0x1800016ee  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016f3  jmp     short loc_1800016E1
0x1800016f5  mov     al, 1
0x1800016f7  add     rsp, 28h
0x1800016fb  retn
```
