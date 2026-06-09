# dllmain_crt_process_detach

- ea: `0x180007528`
- end: `0x1800075ab`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800073d0`

## callees

- `0x180007528`
- `0x180007834`
- `0x18000786c`
- `0x180007994`
- `0x1800079cc`
- `0x180007b5c`
- `0x180007b88`
- `0x180007bc8`
- `0x180007c18`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_18002B4D0 <= 0 )
    return 0;
  --dword_18002B4D0;
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
0x180007528  mov     [rsp+arg_0], rbx
0x18000752d  push    rdi
0x18000752e  sub     rsp, 30h
0x180007532  mov     dil, cl
0x180007535  mov     eax, cs:dword_18002B4D0
0x18000753b  test    eax, eax
0x18000753d  jg      short loc_18000754C
0x18000753f  xor     eax, eax
0x180007541  mov     rbx, [rsp+38h+arg_0]
0x180007546  add     rsp, 30h
0x18000754a  pop     rdi
0x18000754b  retn
0x18000754c  dec     eax
0x18000754e  mov     cs:dword_18002B4D0, eax
0x180007554  call    __scrt_acquire_startup_lock
0x180007559  mov     bl, al
0x18000755b  mov     [rsp+38h+var_18], al
0x18000755f  cmp     cs:__scrt_current_native_startup_state, 2
0x180007566  jnz     short loc_18000759E
0x180007568  call    __scrt_dllmain_uninitialize_c
0x18000756d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180007572  call    _RTC_Terminate
0x180007577  mov     cs:__scrt_current_native_startup_state, 0
0x180007581  mov     cl, bl
0x180007583  call    __scrt_release_startup_lock
0x180007588  xor     edx, edx
0x18000758a  mov     cl, dil
0x18000758d  call    __scrt_uninitialize_crt
0x180007592  movzx   ebx, al
0x180007595  call    __scrt_dllmain_uninitialize_critical
0x18000759a  mov     eax, ebx
0x18000759c  jmp     short loc_180007541
0x18000759e  mov     ecx, 7
0x1800075a3  call    __scrt_fastfail
0x18001e4d9  push    rbp
0x18001e4db  sub     rsp, 20h
0x18001e4df  mov     rbp, rdx
0x18001e4e2  mov     cl, [rbp+20h]
0x18001e4e5  call    __scrt_release_startup_lock
0x18001e4ea  nop
0x18001e4eb  add     rsp, 20h
0x18001e4ef  pop     rbp
0x18001e4f0  retn
0x18001e4f2  push    rbp
0x18001e4f4  sub     rsp, 20h
0x18001e4f8  mov     rbp, rdx
0x18001e4fb  add     rsp, 20h
0x18001e4ff  pop     rbp
0x18001e500  jmp     __scrt_dllmain_uninitialize_critical
```
