# __scrt_dllmain_crt_thread_attach

- ea: `0x180014224`
- end: `0x18001424c`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180013db0`

## callees

- `0x180014224`
- `0x1800151e0`

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
0x180014224  sub     rsp, 28h
0x180014228  call    __scrt_stub_for_acrt_uninitialize_critical
0x18001422d  test    al, al
0x18001422f  jnz     short loc_180014235
0x180014231  xor     al, al
0x180014233  jmp     short loc_180014247
0x180014235  call    __scrt_stub_for_acrt_uninitialize_critical
0x18001423a  test    al, al
0x18001423c  jnz     short loc_180014245
0x18001423e  call    __scrt_stub_for_acrt_uninitialize_critical
0x180014243  jmp     short loc_180014231
0x180014245  mov     al, 1
0x180014247  add     rsp, 28h
0x18001424b  retn
```
