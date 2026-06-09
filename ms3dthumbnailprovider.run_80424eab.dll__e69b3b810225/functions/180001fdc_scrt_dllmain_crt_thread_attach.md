# __scrt_dllmain_crt_thread_attach

- ea: `0x180001fdc`
- end: `0x180002004`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001b80`

## callees

- `0x180001fdc`
- `0x1800029c0`

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
0x180001fdc  sub     rsp, 28h
0x180001fe0  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001fe5  test    al, al
0x180001fe7  jnz     short loc_180001FED
0x180001fe9  xor     al, al
0x180001feb  jmp     short loc_180001FFF
0x180001fed  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001ff2  test    al, al
0x180001ff4  jnz     short loc_180001FFD
0x180001ff6  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001ffb  jmp     short loc_180001FE9
0x180001ffd  mov     al, 1
0x180001fff  add     rsp, 28h
0x180002003  retn
```
