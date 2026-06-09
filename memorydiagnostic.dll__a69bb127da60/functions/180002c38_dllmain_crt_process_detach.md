# dllmain_crt_process_detach

- ea: `0x180002c38`
- end: `0x180002cbb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180002ae0`

## callees

- `0x180002c38`
- `0x180002edc`
- `0x180003004`
- `0x18000303c`
- `0x1800031cc`
- `0x1800031f8`
- `0x1800036c4`
- `0x18000370c`
- `0x18000375c`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_18002F530 <= 0 )
    return 0;
  --dword_18002F530;
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
0x180002c38  mov     [rsp+arg_0], rbx
0x180002c3d  push    rdi
0x180002c3e  sub     rsp, 30h
0x180002c42  mov     dil, cl
0x180002c45  mov     eax, cs:dword_18002F530
0x180002c4b  test    eax, eax
0x180002c4d  jg      short loc_180002C5C
0x180002c4f  xor     eax, eax
0x180002c51  mov     rbx, [rsp+38h+arg_0]
0x180002c56  add     rsp, 30h
0x180002c5a  pop     rdi
0x180002c5b  retn
0x180002c5c  dec     eax
0x180002c5e  mov     cs:dword_18002F530, eax
0x180002c64  call    __scrt_acquire_startup_lock
0x180002c69  mov     bl, al
0x180002c6b  mov     [rsp+38h+var_18], al
0x180002c6f  cmp     cs:__scrt_current_native_startup_state, 2
0x180002c76  jnz     short loc_180002CAE
0x180002c78  call    __scrt_dllmain_uninitialize_c
0x180002c7d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180002c82  call    _RTC_Terminate
0x180002c87  mov     cs:__scrt_current_native_startup_state, 0
0x180002c91  mov     cl, bl
0x180002c93  call    __scrt_release_startup_lock
0x180002c98  xor     edx, edx
0x180002c9a  mov     cl, dil
0x180002c9d  call    __scrt_uninitialize_crt
0x180002ca2  movzx   ebx, al
0x180002ca5  call    __scrt_dllmain_uninitialize_critical
0x180002caa  mov     eax, ebx
0x180002cac  jmp     short loc_180002C51
0x180002cae  mov     ecx, 7
0x180002cb3  call    __scrt_fastfail
0x180020919  push    rbp
0x18002091b  sub     rsp, 20h
0x18002091f  mov     rbp, rdx
0x180020922  mov     cl, [rbp+20h]
0x180020925  call    __scrt_release_startup_lock
0x18002092a  nop
0x18002092b  add     rsp, 20h
0x18002092f  pop     rbp
0x180020930  retn
0x180020932  push    rbp
0x180020934  sub     rsp, 20h
0x180020938  mov     rbp, rdx
0x18002093b  add     rsp, 20h
0x18002093f  pop     rbp
0x180020940  jmp     __scrt_dllmain_uninitialize_critical
```
