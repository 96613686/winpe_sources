# dllmain_crt_process_detach

- ea: `0x180001ac8`
- end: `0x180001b4b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001970`

## callees

- `0x180001ac8`
- `0x180001d4c`
- `0x180001e74`
- `0x180001eac`
- `0x18000203c`
- `0x180002068`
- `0x1800021f4`
- `0x18000223c`
- `0x18000228c`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_18001B610 <= 0 )
    return 0;
  --dword_18001B610;
  v3 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
    _scrt_fastfail(7u);
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
0x180001ac8  mov     [rsp+arg_0], rbx
0x180001acd  push    rdi
0x180001ace  sub     rsp, 30h
0x180001ad2  mov     dil, cl
0x180001ad5  mov     eax, cs:dword_18001B610
0x180001adb  test    eax, eax
0x180001add  jg      short loc_180001AEC
0x180001adf  xor     eax, eax
0x180001ae1  mov     rbx, [rsp+38h+arg_0]
0x180001ae6  add     rsp, 30h
0x180001aea  pop     rdi
0x180001aeb  retn
0x180001aec  dec     eax
0x180001aee  mov     cs:dword_18001B610, eax
0x180001af4  call    __scrt_acquire_startup_lock
0x180001af9  mov     bl, al
0x180001afb  mov     [rsp+38h+var_18], al
0x180001aff  cmp     cs:__scrt_current_native_startup_state, 2
0x180001b06  jnz     short loc_180001B3E
0x180001b08  call    __scrt_dllmain_uninitialize_c
0x180001b0d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001b12  call    _RTC_Terminate
0x180001b17  mov     cs:__scrt_current_native_startup_state, 0
0x180001b21  mov     cl, bl
0x180001b23  call    __scrt_release_startup_lock
0x180001b28  xor     edx, edx
0x180001b2a  mov     cl, dil
0x180001b2d  call    __scrt_uninitialize_crt
0x180001b32  movzx   ebx, al
0x180001b35  call    __scrt_dllmain_uninitialize_critical
0x180001b3a  mov     eax, ebx
0x180001b3c  jmp     short loc_180001AE1
0x180001b3e  mov     ecx, 7
0x180001b43  call    __scrt_fastfail
0x180011d09  push    rbp
0x180011d0b  sub     rsp, 20h
0x180011d0f  mov     rbp, rdx
0x180011d12  mov     cl, [rbp+20h]
0x180011d15  call    __scrt_release_startup_lock
0x180011d1a  nop
0x180011d1b  add     rsp, 20h
0x180011d1f  pop     rbp
0x180011d20  retn
0x180011d22  push    rbp
0x180011d24  sub     rsp, 20h
0x180011d28  mov     rbp, rdx
0x180011d2b  add     rsp, 20h
0x180011d2f  pop     rbp
0x180011d30  jmp     __scrt_dllmain_uninitialize_critical
```
