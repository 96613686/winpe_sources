# dllmain_crt_process_detach

- ea: `0x18000a308`
- end: `0x18000a38b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18000a1b0`

## callees

- `0x18000a308`
- `0x18000a544`
- `0x18000a66c`
- `0x18000a6a4`
- `0x18000a834`
- `0x18000a860`
- `0x18000a9fc`
- `0x18000aa44`
- `0x18000aa94`

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

  if ( dword_18002DAD0 <= 0 )
    return 0;
  --dword_18002DAD0;
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
0x18000a308  mov     [rsp+arg_0], rbx
0x18000a30d  push    rdi
0x18000a30e  sub     rsp, 30h
0x18000a312  mov     dil, cl
0x18000a315  mov     eax, cs:dword_18002DAD0
0x18000a31b  test    eax, eax
0x18000a31d  jg      short loc_18000A32C
0x18000a31f  xor     eax, eax
0x18000a321  mov     rbx, [rsp+38h+arg_0]
0x18000a326  add     rsp, 30h
0x18000a32a  pop     rdi
0x18000a32b  retn
0x18000a32c  dec     eax
0x18000a32e  mov     cs:dword_18002DAD0, eax
0x18000a334  call    __scrt_acquire_startup_lock
0x18000a339  mov     bl, al
0x18000a33b  mov     [rsp+38h+var_18], al
0x18000a33f  cmp     cs:__scrt_current_native_startup_state, 2
0x18000a346  jnz     short loc_18000A37E
0x18000a348  call    __scrt_dllmain_uninitialize_c
0x18000a34d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x18000a352  call    _RTC_Terminate
0x18000a357  mov     cs:__scrt_current_native_startup_state, 0
0x18000a361  mov     cl, bl
0x18000a363  call    __scrt_release_startup_lock
0x18000a368  xor     edx, edx
0x18000a36a  mov     cl, dil
0x18000a36d  call    __scrt_uninitialize_crt
0x18000a372  movzx   ebx, al
0x18000a375  call    __scrt_dllmain_uninitialize_critical
0x18000a37a  mov     eax, ebx
0x18000a37c  jmp     short loc_18000A321
0x18000a37e  mov     ecx, 7
0x18000a383  call    __scrt_fastfail
0x18001e965  push    rbp
0x18001e967  sub     rsp, 20h
0x18001e96b  mov     rbp, rdx
0x18001e96e  mov     cl, [rbp+20h]
0x18001e971  call    __scrt_release_startup_lock
0x18001e976  nop
0x18001e977  add     rsp, 20h
0x18001e97b  pop     rbp
0x18001e97c  retn
0x18001e97e  push    rbp
0x18001e980  sub     rsp, 20h
0x18001e984  mov     rbp, rdx
0x18001e987  add     rsp, 20h
0x18001e98b  pop     rbp
0x18001e98c  jmp     __scrt_dllmain_uninitialize_critical
```
