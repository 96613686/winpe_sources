# __scrt_dllmain_crt_thread_attach

- ea: `0x180001618`
- end: `0x180001640`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800010f0`

## callees

- `0x180001618`
- `0x180001d5c`

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
0x180001618  sub     rsp, 28h
0x18000161c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001621  test    al, al
0x180001623  jnz     short loc_180001629
0x180001625  xor     al, al
0x180001627  jmp     short loc_18000163B
0x180001629  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000162e  test    al, al
0x180001630  jnz     short loc_180001639
0x180001632  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001637  jmp     short loc_180001625
0x180001639  mov     al, 1
0x18000163b  add     rsp, 28h
0x18000163f  retn
```
