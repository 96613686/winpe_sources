# dllmain_crt_process_detach

- ea: `0x180002278`
- end: `0x1800022fb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180002120`

## callees

- `0x180002278`
- `0x1800024b4`
- `0x1800025dc`
- `0x180002614`
- `0x1800027a4`
- `0x1800027d0`
- `0x1800029dc`
- `0x180002a24`
- `0x180002a74`

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

  if ( dword_18003F570 <= 0 )
    return 0;
  --dword_18003F570;
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
0x180002278  mov     [rsp+arg_0], rbx
0x18000227d  push    rdi
0x18000227e  sub     rsp, 30h
0x180002282  mov     dil, cl
0x180002285  mov     eax, cs:dword_18003F570
0x18000228b  test    eax, eax
0x18000228d  jg      short loc_18000229C
0x18000228f  xor     eax, eax
0x180002291  mov     rbx, [rsp+38h+arg_0]
0x180002296  add     rsp, 30h
0x18000229a  pop     rdi
0x18000229b  retn
0x18000229c  dec     eax
0x18000229e  mov     cs:dword_18003F570, eax
0x1800022a4  call    __scrt_acquire_startup_lock
0x1800022a9  mov     bl, al
0x1800022ab  mov     [rsp+38h+var_18], al
0x1800022af  cmp     cs:__scrt_current_native_startup_state, 2
0x1800022b6  jnz     short loc_1800022EE
0x1800022b8  call    __scrt_dllmain_uninitialize_c
0x1800022bd  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800022c2  call    _RTC_Terminate
0x1800022c7  mov     cs:__scrt_current_native_startup_state, 0
0x1800022d1  mov     cl, bl
0x1800022d3  call    __scrt_release_startup_lock
0x1800022d8  xor     edx, edx
0x1800022da  mov     cl, dil
0x1800022dd  call    __scrt_uninitialize_crt
0x1800022e2  movzx   ebx, al
0x1800022e5  call    __scrt_dllmain_uninitialize_critical
0x1800022ea  mov     eax, ebx
0x1800022ec  jmp     short loc_180002291
0x1800022ee  mov     ecx, 7
0x1800022f3  call    __scrt_fastfail
0x18002e099  push    rbp
0x18002e09b  sub     rsp, 20h
0x18002e09f  mov     rbp, rdx
0x18002e0a2  mov     cl, [rbp+20h]
0x18002e0a5  call    __scrt_release_startup_lock
0x18002e0aa  nop
0x18002e0ab  add     rsp, 20h
0x18002e0af  pop     rbp
0x18002e0b0  retn
0x18002e0b2  push    rbp
0x18002e0b4  sub     rsp, 20h
0x18002e0b8  mov     rbp, rdx
0x18002e0bb  add     rsp, 20h
0x18002e0bf  pop     rbp
0x18002e0c0  jmp     __scrt_dllmain_uninitialize_critical
```
