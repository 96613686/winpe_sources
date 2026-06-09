# __scrt_dllmain_crt_thread_attach

- ea: `0x180001510`
- end: `0x180001538`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800010f0`

## callees

- `0x180001510`
- `0x180001df8`

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
0x180001510  sub     rsp, 28h
0x180001514  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001519  test    al, al
0x18000151b  jnz     short loc_180001521
0x18000151d  xor     al, al
0x18000151f  jmp     short loc_180001533
0x180001521  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001526  test    al, al
0x180001528  jnz     short loc_180001531
0x18000152a  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000152f  jmp     short loc_18000151D
0x180001531  mov     al, 1
0x180001533  add     rsp, 28h
0x180001537  retn
```
