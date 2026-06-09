# __scrt_dllmain_crt_thread_attach

- ea: `0x180002280`
- end: `0x1800022a8`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001e60`

## callees

- `0x180002280`
- `0x180003968`

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
0x180002280  sub     rsp, 28h
0x180002284  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002289  test    al, al
0x18000228b  jnz     short loc_180002291
0x18000228d  xor     al, al
0x18000228f  jmp     short loc_1800022A3
0x180002291  call    __scrt_stub_for_acrt_uninitialize_critical
0x180002296  test    al, al
0x180002298  jnz     short loc_1800022A1
0x18000229a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000229f  jmp     short loc_18000228D
0x1800022a1  mov     al, 1
0x1800022a3  add     rsp, 28h
0x1800022a7  retn
```
