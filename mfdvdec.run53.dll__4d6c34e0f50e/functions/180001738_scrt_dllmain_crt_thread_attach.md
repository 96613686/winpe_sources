# __scrt_dllmain_crt_thread_attach

- ea: `0x180001738`
- end: `0x180001760`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001210`

## callees

- `0x180001738`
- `0x180001ebc`

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
0x180001738  sub     rsp, 28h
0x18000173c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001741  test    al, al
0x180001743  jnz     short loc_180001749
0x180001745  xor     al, al
0x180001747  jmp     short loc_18000175B
0x180001749  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000174e  test    al, al
0x180001750  jnz     short loc_180001759
0x180001752  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001757  jmp     short loc_180001745
0x180001759  mov     al, 1
0x18000175b  add     rsp, 28h
0x18000175f  retn
```
