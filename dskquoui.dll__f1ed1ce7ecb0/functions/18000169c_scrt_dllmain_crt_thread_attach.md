# __scrt_dllmain_crt_thread_attach

- ea: `0x18000169c`
- end: `0x1800016c4`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800011a0`

## callees

- `0x18000169c`
- `0x180002368`

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
0x18000169c  sub     rsp, 28h
0x1800016a0  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016a5  test    al, al
0x1800016a7  jnz     short loc_1800016AD
0x1800016a9  xor     al, al
0x1800016ab  jmp     short loc_1800016BF
0x1800016ad  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016b2  test    al, al
0x1800016b4  jnz     short loc_1800016BD
0x1800016b6  call    __scrt_stub_for_acrt_uninitialize_critical
0x1800016bb  jmp     short loc_1800016A9
0x1800016bd  mov     al, 1
0x1800016bf  add     rsp, 28h
0x1800016c3  retn
```
