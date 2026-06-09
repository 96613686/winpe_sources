# dllmain_crt_process_detach

- ea: `0x180001d78`
- end: `0x180001dfb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001c20`

## callees

- `0x180001d78`
- `0x180002020`
- `0x180002148`
- `0x180002180`
- `0x180002310`
- `0x18000233c`
- `0x1800025b0`
- `0x1800025f8`
- `0x180002648`

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

  if ( dword_18001A4D0 <= 0 )
    return 0;
  --dword_18001A4D0;
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
0x180001d78  mov     [rsp+arg_0], rbx
0x180001d7d  push    rdi
0x180001d7e  sub     rsp, 30h
0x180001d82  mov     dil, cl
0x180001d85  mov     eax, cs:dword_18001A4D0
0x180001d8b  test    eax, eax
0x180001d8d  jg      short loc_180001D9C
0x180001d8f  xor     eax, eax
0x180001d91  mov     rbx, [rsp+38h+arg_0]
0x180001d96  add     rsp, 30h
0x180001d9a  pop     rdi
0x180001d9b  retn
0x180001d9c  dec     eax
0x180001d9e  mov     cs:dword_18001A4D0, eax
0x180001da4  call    __scrt_acquire_startup_lock
0x180001da9  mov     bl, al
0x180001dab  mov     [rsp+38h+var_18], al
0x180001daf  cmp     cs:__scrt_current_native_startup_state, 2
0x180001db6  jnz     short loc_180001DEE
0x180001db8  call    __scrt_dllmain_uninitialize_c
0x180001dbd  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001dc2  call    _RTC_Terminate
0x180001dc7  mov     cs:__scrt_current_native_startup_state, 0
0x180001dd1  mov     cl, bl
0x180001dd3  call    __scrt_release_startup_lock
0x180001dd8  xor     edx, edx
0x180001dda  mov     cl, dil
0x180001ddd  call    __scrt_uninitialize_crt
0x180001de2  movzx   ebx, al
0x180001de5  call    __scrt_dllmain_uninitialize_critical
0x180001dea  mov     eax, ebx
0x180001dec  jmp     short loc_180001D91
0x180001dee  mov     ecx, 7
0x180001df3  call    __scrt_fastfail
0x180012469  push    rbp
0x18001246b  sub     rsp, 20h
0x18001246f  mov     rbp, rdx
0x180012472  mov     cl, [rbp+20h]
0x180012475  call    __scrt_release_startup_lock
0x18001247a  nop
0x18001247b  add     rsp, 20h
0x18001247f  pop     rbp
0x180012480  retn
0x180012482  push    rbp
0x180012484  sub     rsp, 20h
0x180012488  mov     rbp, rdx
0x18001248b  add     rsp, 20h
0x18001248f  pop     rbp
0x180012490  jmp     __scrt_dllmain_uninitialize_critical
```
