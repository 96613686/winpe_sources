# __scrt_dllmain_crt_thread_attach

- ea: `0x180004df8`
- end: `0x180004e20`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800048d0`

## callees

- `0x180004df8`
- `0x180005640`

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
0x180004df8  sub     rsp, 28h
0x180004dfc  call    __scrt_stub_for_acrt_uninitialize_critical
0x180004e01  test    al, al
0x180004e03  jnz     short loc_180004E09
0x180004e05  xor     al, al
0x180004e07  jmp     short loc_180004E1B
0x180004e09  call    __scrt_stub_for_acrt_uninitialize_critical
0x180004e0e  test    al, al
0x180004e10  jnz     short loc_180004E19
0x180004e12  call    __scrt_stub_for_acrt_uninitialize_critical
0x180004e17  jmp     short loc_180004E05
0x180004e19  mov     al, 1
0x180004e1b  add     rsp, 28h
0x180004e1f  retn
```
