# __scrt_dllmain_crt_thread_attach

- ea: `0x180003c48`
- end: `0x180003c70`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003720`

## callees

- `0x180003c48`
- `0x180004554`

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
0x180003c48  sub     rsp, 28h
0x180003c4c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003c51  test    al, al
0x180003c53  jnz     short loc_180003C59
0x180003c55  xor     al, al
0x180003c57  jmp     short loc_180003C6B
0x180003c59  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003c5e  test    al, al
0x180003c60  jnz     short loc_180003C69
0x180003c62  call    __scrt_stub_for_acrt_uninitialize_critical
0x180003c67  jmp     short loc_180003C55
0x180003c69  mov     al, 1
0x180003c6b  add     rsp, 28h
0x180003c6f  retn
```
