# __scrt_dllmain_crt_thread_attach

- ea: `0x180001dd8`
- end: `0x180001e00`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001970`

## callees

- `0x180001dd8`
- `0x180002cdc`

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
0x180001dd8  sub     rsp, 28h
0x180001ddc  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001de1  test    al, al
0x180001de3  jnz     short loc_180001DE9
0x180001de5  xor     al, al
0x180001de7  jmp     short loc_180001DFB
0x180001de9  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001dee  test    al, al
0x180001df0  jnz     short loc_180001DF9
0x180001df2  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001df7  jmp     short loc_180001DE5
0x180001df9  mov     al, 1
0x180001dfb  add     rsp, 28h
0x180001dff  retn
```
