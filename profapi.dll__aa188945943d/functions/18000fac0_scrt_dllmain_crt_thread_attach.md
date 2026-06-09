# __scrt_dllmain_crt_thread_attach

- ea: `0x18000fac0`
- end: `0x18000fae8`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000f6a0`

## callees

- `0x18000fac0`
- `0x180010860`

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
0x18000fac0  sub     rsp, 28h
0x18000fac4  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000fac9  test    al, al
0x18000facb  jnz     short loc_18000FAD1
0x18000facd  xor     al, al
0x18000facf  jmp     short loc_18000FAE3
0x18000fad1  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000fad6  test    al, al
0x18000fad8  jnz     short loc_18000FAE1
0x18000fada  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000fadf  jmp     short loc_18000FACD
0x18000fae1  mov     al, 1
0x18000fae3  add     rsp, 28h
0x18000fae7  retn
```
