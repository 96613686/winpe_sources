# __scrt_dllmain_crt_thread_attach

- ea: `0x180004404`
- end: `0x18000442c`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003f90`

## callees

- `0x180004404`
- `0x180004db4`

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
0x180004404  sub     rsp, 28h
0x180004408  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000440d  test    al, al
0x18000440f  jnz     short loc_180004415
0x180004411  xor     al, al
0x180004413  jmp     short loc_180004427
0x180004415  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000441a  test    al, al
0x18000441c  jnz     short loc_180004425
0x18000441e  call    __scrt_stub_for_acrt_uninitialize_critical
0x180004423  jmp     short loc_180004411
0x180004425  mov     al, 1
0x180004427  add     rsp, 28h
0x18000442b  retn
```
