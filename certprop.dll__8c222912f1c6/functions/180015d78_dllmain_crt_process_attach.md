# dllmain_crt_process_attach

- ea: `0x180015d78`
- end: `0x180015e72`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180015d20`

## callees

- `0x180015d78`
- `0x180016208`
- `0x180016230`
- `0x180016254`
- `0x180016294`
- `0x1800162d0`
- `0x1800163d0`
- `0x1800164a4`
- `0x180016544`
- `0x1800165a0`
- `0x1800165b0`
- `0x1800165bc`
- `0x180016976`
- `0x180016982`
- `0x180026010`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_attach(__int64 a1, __int64 a2)
{
  char v4; // bl
  char v5; // di
  __int64 v6; // rcx
  void (__fastcall **dyn_tls_init_callback)(__int64, __int64, __int64); // rax
  void (__fastcall **v8)(__int64, __int64, __int64); // rbx

  if ( !(unsigned __int8)_scrt_initialize_crt(0) )
    return 0;
  v4 = _scrt_acquire_startup_lock();
  v5 = 1;
  if ( _scrt_current_native_startup_state )
    _scrt_fastfail(7);
  _scrt_current_native_startup_state = 1;
  if ( (unsigned __int8)_scrt_dllmain_before_initialize_c() )
  {
    RTC_Initialize();
    __scrt_initialize_type_info();
    _scrt_initialize_default_local_stdio_options();
    if ( !initterm_e_0((_PIFV *)&_xi_a, (_PIFV *)&_xi_z) )
    {
      if ( _scrt_dllmain_after_initialize_c() )
      {
        initterm_0((_PVFV *)&_xc_a, (_PVFV *)&_xc_z);
        _scrt_current_native_startup_state = 2;
        v5 = 0;
      }
    }
  }
  LOBYTE(v6) = v4;
  _scrt_release_startup_lock(v6);
  if ( v5 )
    return 0;
  dyn_tls_init_callback = (void (__fastcall **)(__int64, __int64, __int64))_scrt_get_dyn_tls_init_callback();
  v8 = dyn_tls_init_callback;
  if ( *dyn_tls_init_callback )
  {
    if ( (unsigned __int8)_scrt_is_nonwritable_in_current_image(dyn_tls_init_callback) )
      (*v8)(a1, 2, a2);
  }
  ++dword_1800312F0;
  return 1;
}

```

## disassembly

```asm
0x180015d78  push    rbx
0x180015d7a  push    rsi
0x180015d7b  push    rdi
0x180015d7c  push    r14
0x180015d7e  sub     rsp, 28h
0x180015d82  mov     rsi, rdx
0x180015d85  mov     r14, rcx
0x180015d88  xor     ecx, ecx
0x180015d8a  call    __scrt_initialize_crt
0x180015d8f  test    al, al
0x180015d91  jz      loc_180015E5A
0x180015d97  call    __scrt_acquire_startup_lock
0x180015d9c  mov     bl, al
0x180015d9e  mov     [rsp+48h+arg_10], al
0x180015da2  mov     dil, 1
0x180015da5  cmp     cs:__scrt_current_native_startup_state, 0
0x180015dac  jnz     loc_180015E66
0x180015db2  mov     cs:__scrt_current_native_startup_state, 1
0x180015dbc  call    __scrt_dllmain_before_initialize_c
0x180015dc1  test    al, al
0x180015dc3  jz      short loc_180015E14
0x180015dc5  call    _RTC_Initialize
0x180015dca  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180015dcf  call    __scrt_initialize_default_local_stdio_options
0x180015dd4  lea     rdx, __xi_z; Last
0x180015ddb  lea     rcx, __xi_a; First
0x180015de2  call    _initterm_e_0
0x180015de7  test    eax, eax
0x180015de9  jnz     short loc_180015E14
0x180015deb  call    __scrt_dllmain_after_initialize_c
0x180015df0  test    al, al
0x180015df2  jz      short loc_180015E14
0x180015df4  lea     rdx, __xc_z; Last
0x180015dfb  lea     rcx, __xc_a; First
0x180015e02  call    _initterm_0
0x180015e07  mov     cs:__scrt_current_native_startup_state, 2
0x180015e11  xor     dil, dil
0x180015e14  mov     cl, bl
0x180015e16  call    __scrt_release_startup_lock
0x180015e1b  test    dil, dil
0x180015e1e  jnz     short loc_180015E5A
0x180015e20  call    __scrt_get_dyn_tls_init_callback
0x180015e25  mov     rbx, rax
0x180015e28  cmp     qword ptr [rax], 0
0x180015e2c  jz      short loc_180015E4D
0x180015e2e  mov     rcx, rax
0x180015e31  call    __scrt_is_nonwritable_in_current_image
0x180015e36  test    al, al
0x180015e38  jz      short loc_180015E4D
0x180015e3a  mov     r8, rsi
0x180015e3d  mov     edx, 2
0x180015e42  mov     rcx, r14
0x180015e45  mov     rax, [rbx]
0x180015e48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e4d  inc     cs:dword_1800312F0
0x180015e53  mov     eax, 1
0x180015e58  jmp     short loc_180015E5C
0x180015e5a  xor     eax, eax
0x180015e5c  add     rsp, 28h
0x180015e60  pop     r14
0x180015e62  pop     rdi
0x180015e63  pop     rsi
0x180015e64  pop     rbx
0x180015e65  retn
0x180015e66  mov     ecx, 7
0x180015e6b  call    __scrt_fastfail
0x18002513d  push    rbp
0x18002513f  sub     rsp, 20h
0x180025143  mov     rbp, rdx
0x180025146  mov     cl, [rbp+60h]
0x180025149  add     rsp, 20h
0x18002514d  pop     rbp
0x18002514e  jmp     __scrt_release_startup_lock
```
