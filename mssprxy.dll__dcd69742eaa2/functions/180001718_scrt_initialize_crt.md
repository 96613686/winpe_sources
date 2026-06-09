# __scrt_initialize_crt

- ea: `0x180001718`
- end: `0x180001752`
- name: `__scrt_initialize_crt`
- size: `58`
- prototype: `char __fastcall(int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001158`

## callees

- `0x180001718`
- `0x1800019b0`
- `0x1800020ec`

## pseudocode

```c
char __fastcall _scrt_initialize_crt(int a1)
{
  __int64 v1; // rcx
  __int64 v2; // rcx

  if ( !a1 )
    byte_18002A0F1 = 1;
  _isa_available_init();
  if ( !(unsigned __int8)_scrt_stub_for_acrt_uninitialize_critical(v1) )
    return 0;
  if ( !(unsigned __int8)_scrt_stub_for_acrt_uninitialize_critical(v2) )
  {
    _scrt_stub_for_acrt_uninitialize_critical(0);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180001718  sub     rsp, 28h
0x18000171c  test    ecx, ecx
0x18000171e  jnz     short loc_180001727
0x180001720  mov     cs:byte_18002A0F1, 1
0x180001727  call    __isa_available_init
0x18000172c  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001731  test    al, al
0x180001733  jnz     short loc_180001739
0x180001735  xor     al, al
0x180001737  jmp     short loc_18000174D
0x180001739  call    __scrt_stub_for_acrt_uninitialize_critical
0x18000173e  test    al, al
0x180001740  jnz     short loc_18000174B
0x180001742  xor     ecx, ecx
0x180001744  call    __scrt_stub_for_acrt_uninitialize_critical
0x180001749  jmp     short loc_180001735
0x18000174b  mov     al, 1
0x18000174d  add     rsp, 28h
0x180001751  retn
```
