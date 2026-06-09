# __scrt_dllmain_crt_thread_attach

- ea: `0x180009444`
- end: `0x18000946c`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180008f00`

## callees

- `0x180009444`
- `0x18000ac94`

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
0x180009444  sub     rsp, 28h
0x180009448  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000944d  test    al, al
0x18000944f  jnz     short loc_180009455
0x180009451  xor     al, al
0x180009453  jmp     short loc_180009467
0x180009455  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000945a  test    al, al
0x18000945c  jnz     short loc_180009465
0x18000945e  call    __scrt_stub_for_acrt_uninitialize_critical
0x180009463  jmp     short loc_180009451
0x180009465  mov     al, 1
0x180009467  add     rsp, 28h
0x18000946b  retn
```
