# __scrt_dllmain_crt_thread_attach

- ea: `0x180001610`
- end: `0x180001638`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001090`

## callees

- `0x180001610`
- `0x180001d2c`

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
0x180001610  sub     rsp, 28h
0x180001614  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001619  test    al, al
0x18000161b  jnz     short loc_180001621
0x18000161d  xor     al, al
0x18000161f  jmp     short loc_180001633
0x180001621  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001626  test    al, al
0x180001628  jnz     short loc_180001631
0x18000162a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000162f  jmp     short loc_18000161D
0x180001631  mov     al, 1
0x180001633  add     rsp, 28h
0x180001637  retn
```
