# __scrt_dllmain_crt_thread_attach

- ea: `0x180001628`
- end: `0x180001650`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800011a0`

## callees

- `0x180001628`
- `0x180002218`

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
0x180001628  sub     rsp, 28h
0x18000162c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001631  test    al, al
0x180001633  jnz     short loc_180001639
0x180001635  xor     al, al
0x180001637  jmp     short loc_18000164B
0x180001639  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000163e  test    al, al
0x180001640  jnz     short loc_180001649
0x180001642  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001647  jmp     short loc_180001635
0x180001649  mov     al, 1
0x18000164b  add     rsp, 28h
0x18000164f  retn
```
