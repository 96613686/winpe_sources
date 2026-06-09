# dllmain_crt_process_detach

- ea: `0x180001568`
- end: `0x1800015eb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001410`

## callees

- `0x180001568`
- `0x1800017dc`
- `0x180001904`
- `0x18000193c`
- `0x180001acc`
- `0x180001af8`
- `0x180001b9c`
- `0x180001ca0`
- `0x180001cf0`

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

  if ( dword_180015390 <= 0 )
    return 0;
  --dword_180015390;
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
0x180001568  mov     [rsp+arg_0], rbx
0x18000156d  push    rdi
0x18000156e  sub     rsp, 30h
0x180001572  mov     dil, cl
0x180001575  mov     eax, cs:dword_180015390
0x18000157b  test    eax, eax
0x18000157d  jg      short loc_18000158C
0x18000157f  xor     eax, eax
0x180001581  mov     rbx, [rsp+38h+arg_0]
0x180001586  add     rsp, 30h
0x18000158a  pop     rdi
0x18000158b  retn
0x18000158c  dec     eax
0x18000158e  mov     cs:dword_180015390, eax
0x180001594  call    __scrt_acquire_startup_lock
0x180001599  mov     bl, al
0x18000159b  mov     [rsp+38h+var_18], al
0x18000159f  cmp     cs:__scrt_current_native_startup_state, 2
0x1800015a6  jnz     short loc_1800015DE
0x1800015a8  call    __scrt_dllmain_uninitialize_c
0x1800015ad  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800015b2  call    _RTC_Terminate
0x1800015b7  mov     cs:__scrt_current_native_startup_state, 0
0x1800015c1  mov     cl, bl
0x1800015c3  call    __scrt_release_startup_lock
0x1800015c8  xor     edx, edx
0x1800015ca  mov     cl, dil
0x1800015cd  call    __scrt_uninitialize_crt
0x1800015d2  movzx   ebx, al
0x1800015d5  call    __scrt_dllmain_uninitialize_critical
0x1800015da  mov     eax, ebx
0x1800015dc  jmp     short loc_180001581
0x1800015de  mov     ecx, 7
0x1800015e3  call    __scrt_fastfail
0x18000dfc9  push    rbp
0x18000dfcb  sub     rsp, 20h
0x18000dfcf  mov     rbp, rdx
0x18000dfd2  mov     cl, [rbp+20h]
0x18000dfd5  call    __scrt_release_startup_lock
0x18000dfda  nop
0x18000dfdb  add     rsp, 20h
0x18000dfdf  pop     rbp
0x18000dfe0  retn
0x18000dfe2  push    rbp
0x18000dfe4  sub     rsp, 20h
0x18000dfe8  mov     rbp, rdx
0x18000dfeb  add     rsp, 20h
0x18000dfef  pop     rbp
0x18000dff0  jmp     __scrt_dllmain_uninitialize_critical
```
