# dllmain_crt_process_detach

- ea: `0x1800028f8`
- end: `0x18000297b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800027a0`

## callees

- `0x1800028f8`
- `0x180002b34`
- `0x180002c5c`
- `0x180002c94`
- `0x180002e24`
- `0x180002e50`
- `0x180003060`
- `0x1800030a8`
- `0x1800030f8`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  __int64 v3; // rcx
  char v4; // bl
  __int64 v5; // rcx
  __int64 v6; // rcx
  unsigned int v7; // ebx
  __int64 v8; // rcx

  if ( dword_180026310 <= 0 )
    return 0;
  --dword_180026310;
  v4 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
    _scrt_fastfail(7);
  _scrt_dllmain_uninitialize_c(v3);
  __scrt_uninitialize_type_info();
  RTC_Terminate();
  _scrt_current_native_startup_state = 0;
  LOBYTE(v5) = v4;
  _scrt_release_startup_lock(v5);
  LOBYTE(v6) = a1;
  v7 = (unsigned __int8)_scrt_uninitialize_crt(v6, 0);
  _scrt_dllmain_uninitialize_critical(v8);
  return v7;
}

```

## disassembly

```asm
0x1800028f8  mov     [rsp+arg_0], rbx
0x1800028fd  push    rdi
0x1800028fe  sub     rsp, 30h
0x180002902  mov     dil, cl
0x180002905  mov     eax, cs:dword_180026310
0x18000290b  test    eax, eax
0x18000290d  jg      short loc_18000291C
0x18000290f  xor     eax, eax
0x180002911  mov     rbx, [rsp+38h+arg_0]
0x180002916  add     rsp, 30h
0x18000291a  pop     rdi
0x18000291b  retn
0x18000291c  dec     eax
0x18000291e  mov     cs:dword_180026310, eax
0x180002924  call    __scrt_acquire_startup_lock
0x180002929  mov     bl, al
0x18000292b  mov     [rsp+38h+var_18], al
0x18000292f  cmp     cs:__scrt_current_native_startup_state, 2
0x180002936  jnz     short loc_18000296E
0x180002938  call    __scrt_dllmain_uninitialize_c
0x18000293d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180002942  call    _RTC_Terminate
0x180002947  mov     cs:__scrt_current_native_startup_state, 0
0x180002951  mov     cl, bl
0x180002953  call    __scrt_release_startup_lock
0x180002958  xor     edx, edx
0x18000295a  mov     cl, dil
0x18000295d  call    __scrt_uninitialize_crt
0x180002962  movzx   ebx, al
0x180002965  call    __scrt_dllmain_uninitialize_critical
0x18000296a  mov     eax, ebx
0x18000296c  jmp     short loc_180002911
0x18000296e  mov     ecx, 7
0x180002973  call    __scrt_fastfail
0x180018809  push    rbp
0x18001880b  sub     rsp, 20h
0x18001880f  mov     rbp, rdx
0x180018812  mov     cl, [rbp+20h]
0x180018815  call    __scrt_release_startup_lock
0x18001881a  nop
0x18001881b  add     rsp, 20h
0x18001881f  pop     rbp
0x180018820  retn
0x180018822  push    rbp
0x180018824  sub     rsp, 20h
0x180018828  mov     rbp, rdx
0x18001882b  add     rsp, 20h
0x18001882f  pop     rbp
0x180018830  jmp     __scrt_dllmain_uninitialize_critical
```
