# dllmain_crt_process_detach

- ea: `0x1800014b8`
- end: `0x18000153b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001360`

## callees

- `0x1800014b8`
- `0x1800016f4`
- `0x18000181c`
- `0x180001854`
- `0x1800019e4`
- `0x180001a10`
- `0x180001d10`
- `0x180001d58`
- `0x180001da8`

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

  if ( dword_18002A450 <= 0 )
    return 0;
  --dword_18002A450;
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
0x1800014b8  mov     [rsp+arg_0], rbx
0x1800014bd  push    rdi
0x1800014be  sub     rsp, 30h
0x1800014c2  mov     dil, cl
0x1800014c5  mov     eax, cs:dword_18002A450
0x1800014cb  test    eax, eax
0x1800014cd  jg      short loc_1800014DC
0x1800014cf  xor     eax, eax
0x1800014d1  mov     rbx, [rsp+38h+arg_0]
0x1800014d6  add     rsp, 30h
0x1800014da  pop     rdi
0x1800014db  retn
0x1800014dc  dec     eax
0x1800014de  mov     cs:dword_18002A450, eax
0x1800014e4  call    __scrt_acquire_startup_lock
0x1800014e9  mov     bl, al
0x1800014eb  mov     [rsp+38h+var_18], al
0x1800014ef  cmp     cs:__scrt_current_native_startup_state, 2
0x1800014f6  jnz     short loc_18000152E
0x1800014f8  call    __scrt_dllmain_uninitialize_c
0x1800014fd  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001502  call    _RTC_Terminate
0x180001507  mov     cs:__scrt_current_native_startup_state, 0
0x180001511  mov     cl, bl
0x180001513  call    __scrt_release_startup_lock
0x180001518  xor     edx, edx
0x18000151a  mov     cl, dil
0x18000151d  call    __scrt_uninitialize_crt
0x180001522  movzx   ebx, al
0x180001525  call    __scrt_dllmain_uninitialize_critical
0x18000152a  mov     eax, ebx
0x18000152c  jmp     short loc_1800014D1
0x18000152e  mov     ecx, 7
0x180001533  call    __scrt_fastfail
0x180021859  push    rbp
0x18002185b  sub     rsp, 20h
0x18002185f  mov     rbp, rdx
0x180021862  mov     cl, [rbp+20h]
0x180021865  call    __scrt_release_startup_lock
0x18002186a  nop
0x18002186b  add     rsp, 20h
0x18002186f  pop     rbp
0x180021870  retn
0x180021872  push    rbp
0x180021874  sub     rsp, 20h
0x180021878  mov     rbp, rdx
0x18002187b  add     rsp, 20h
0x18002187f  pop     rbp
0x180021880  jmp     __scrt_dllmain_uninitialize_critical
```
