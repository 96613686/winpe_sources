# dllmain_crt_process_detach

- ea: `0x18000c5e8`
- end: `0x18000c66b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18000c490`

## callees

- `0x18000c5e8`
- `0x18000c7f4`
- `0x18000c91c`
- `0x18000c954`
- `0x18000cae4`
- `0x18000cb10`
- `0x18000cbf0`
- `0x18000cc38`
- `0x18000cc88`

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

  if ( dword_180025920 <= 0 )
    return 0;
  --dword_180025920;
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
0x18000c5e8  mov     [rsp+arg_0], rbx
0x18000c5ed  push    rdi
0x18000c5ee  sub     rsp, 30h
0x18000c5f2  mov     dil, cl
0x18000c5f5  mov     eax, cs:dword_180025920
0x18000c5fb  test    eax, eax
0x18000c5fd  jg      short loc_18000C60C
0x18000c5ff  xor     eax, eax
0x18000c601  mov     rbx, [rsp+38h+arg_0]
0x18000c606  add     rsp, 30h
0x18000c60a  pop     rdi
0x18000c60b  retn
0x18000c60c  dec     eax
0x18000c60e  mov     cs:dword_180025920, eax
0x18000c614  call    __scrt_acquire_startup_lock
0x18000c619  mov     bl, al
0x18000c61b  mov     [rsp+38h+var_18], al
0x18000c61f  cmp     cs:__scrt_current_native_startup_state, 2
0x18000c626  jnz     short loc_18000C65E
0x18000c628  call    __scrt_dllmain_uninitialize_c
0x18000c62d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x18000c632  call    _RTC_Terminate
0x18000c637  mov     cs:__scrt_current_native_startup_state, 0
0x18000c641  mov     cl, bl
0x18000c643  call    __scrt_release_startup_lock
0x18000c648  xor     edx, edx
0x18000c64a  mov     cl, dil
0x18000c64d  call    __scrt_uninitialize_crt
0x18000c652  movzx   ebx, al
0x18000c655  call    __scrt_dllmain_uninitialize_critical
0x18000c65a  mov     eax, ebx
0x18000c65c  jmp     short loc_18000C601
0x18000c65e  mov     ecx, 7
0x18000c663  call    __scrt_fastfail
0x180018a36  push    rbp
0x180018a38  sub     rsp, 20h
0x180018a3c  mov     rbp, rdx
0x180018a3f  mov     cl, [rbp+20h]
0x180018a42  call    __scrt_release_startup_lock
0x180018a47  nop
0x180018a48  add     rsp, 20h
0x180018a4c  pop     rbp
0x180018a4d  retn
0x180018a4f  push    rbp
0x180018a51  sub     rsp, 20h
0x180018a55  mov     rbp, rdx
0x180018a58  add     rsp, 20h
0x180018a5c  pop     rbp
0x180018a5d  jmp     __scrt_dllmain_uninitialize_critical
```
