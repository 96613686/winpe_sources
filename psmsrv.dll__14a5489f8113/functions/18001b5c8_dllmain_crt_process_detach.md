# dllmain_crt_process_detach

- ea: `0x18001b5c8`
- end: `0x18001b64b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18001b470`

## callees

- `0x18001b5c8`
- `0x18001b900`
- `0x18001b938`
- `0x18001ba60`
- `0x18001ba98`
- `0x18001bc28`
- `0x18001bc54`
- `0x18001bcf4`
- `0x18001bd44`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_18003F310 <= 0 )
    return 0;
  --dword_18003F310;
  v3 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
    _scrt_fastfail(7);
  _scrt_dllmain_uninitialize_c();
  __scrt_uninitialize_type_info();
  RTC_Terminate();
  _scrt_current_native_startup_state = 0;
  LOBYTE(v4) = v3;
  _scrt_release_startup_lock(v4);
  LOBYTE(v5) = a1;
  v6 = (unsigned __int8)_scrt_uninitialize_crt(v5, 0);
  _scrt_dllmain_uninitialize_critical();
  return v6;
}

```

## disassembly

```asm
0x18001b5c8  mov     [rsp+arg_0], rbx
0x18001b5cd  push    rdi
0x18001b5ce  sub     rsp, 30h
0x18001b5d2  mov     dil, cl
0x18001b5d5  mov     eax, cs:dword_18003F310
0x18001b5db  test    eax, eax
0x18001b5dd  jg      short loc_18001B5EC
0x18001b5df  xor     eax, eax
0x18001b5e1  mov     rbx, [rsp+38h+arg_0]
0x18001b5e6  add     rsp, 30h
0x18001b5ea  pop     rdi
0x18001b5eb  retn
0x18001b5ec  dec     eax
0x18001b5ee  mov     cs:dword_18003F310, eax
0x18001b5f4  call    __scrt_acquire_startup_lock
0x18001b5f9  mov     bl, al
0x18001b5fb  mov     [rsp+38h+var_18], al
0x18001b5ff  cmp     cs:__scrt_current_native_startup_state, 2
0x18001b606  jnz     short loc_18001B63E
0x18001b608  call    __scrt_dllmain_uninitialize_c
0x18001b60d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x18001b612  call    _RTC_Terminate
0x18001b617  mov     cs:__scrt_current_native_startup_state, 0
0x18001b621  mov     cl, bl
0x18001b623  call    __scrt_release_startup_lock
0x18001b628  xor     edx, edx
0x18001b62a  mov     cl, dil
0x18001b62d  call    __scrt_uninitialize_crt
0x18001b632  movzx   ebx, al
0x18001b635  call    __scrt_dllmain_uninitialize_critical
0x18001b63a  mov     eax, ebx
0x18001b63c  jmp     short loc_18001B5E1
0x18001b63e  mov     ecx, 7
0x18001b643  call    __scrt_fastfail
0x18002e219  push    rbp
0x18002e21b  sub     rsp, 20h
0x18002e21f  mov     rbp, rdx
0x18002e222  mov     cl, [rbp+20h]
0x18002e225  call    __scrt_release_startup_lock
0x18002e22a  nop
0x18002e22b  add     rsp, 20h
0x18002e22f  pop     rbp
0x18002e230  retn
0x18002e232  push    rbp
0x18002e234  sub     rsp, 20h
0x18002e238  mov     rbp, rdx
0x18002e23b  add     rsp, 20h
0x18002e23f  pop     rbp
0x18002e240  jmp     __scrt_dllmain_uninitialize_critical
```
