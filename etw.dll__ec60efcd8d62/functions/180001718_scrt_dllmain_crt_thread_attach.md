# __scrt_dllmain_crt_thread_attach

- ea: `0x180001718`
- end: `0x180001740`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800011f0`

## callees

- `0x180001718`
- `0x180002328`

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
0x180001718  sub     rsp, 28h
0x18000171c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001721  test    al, al
0x180001723  jnz     short loc_180001729
0x180001725  xor     al, al
0x180001727  jmp     short loc_18000173B
0x180001729  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000172e  test    al, al
0x180001730  jnz     short loc_180001739
0x180001732  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001737  jmp     short loc_180001725
0x180001739  mov     al, 1
0x18000173b  add     rsp, 28h
0x18000173f  retn
```
