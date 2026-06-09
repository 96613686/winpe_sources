# dllmain_crt_process_attach

- ea: `0x18000a208`
- end: `0x18000a302`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x18000a1b0`

## callees

- `0x18000a208`
- `0x18000a544`
- `0x18000a584`
- `0x18000a5c0`
- `0x18000a6c0`
- `0x18000a794`
- `0x18000a834`
- `0x18000a9e8`
- `0x18000aa10`
- `0x18000aa34`
- `0x18000aa44`
- `0x18000aa50`
- `0x18000adb6`
- `0x18000adc2`
- `0x180020010`

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
      if ( (unsigned __int8)_scrt_dllmain_after_initialize_c() )
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
  ++dword_18002DAD0;
  return 1;
}

```

## disassembly

```asm
0x18000a208  push    rbx
0x18000a20a  push    rsi
0x18000a20b  push    rdi
0x18000a20c  push    r14
0x18000a20e  sub     rsp, 28h
0x18000a212  mov     rsi, rdx
0x18000a215  mov     r14, rcx
0x18000a218  xor     ecx, ecx
0x18000a21a  call    __scrt_initialize_crt
0x18000a21f  test    al, al
0x18000a221  jz      loc_18000A2EA
0x18000a227  call    __scrt_acquire_startup_lock
0x18000a22c  mov     bl, al
0x18000a22e  mov     [rsp+48h+arg_10], al
0x18000a232  mov     dil, 1
0x18000a235  cmp     cs:__scrt_current_native_startup_state, 0
0x18000a23c  jnz     loc_18000A2F6
0x18000a242  mov     cs:__scrt_current_native_startup_state, 1
0x18000a24c  call    __scrt_dllmain_before_initialize_c
0x18000a251  test    al, al
0x18000a253  jz      short loc_18000A2A4
0x18000a255  call    _RTC_Initialize
0x18000a25a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000a25f  call    __scrt_initialize_default_local_stdio_options
0x18000a264  lea     rdx, __xi_z; Last
0x18000a26b  lea     rcx, __xi_a; First
0x18000a272  call    _initterm_e_0
0x18000a277  test    eax, eax
0x18000a279  jnz     short loc_18000A2A4
0x18000a27b  call    __scrt_dllmain_after_initialize_c
0x18000a280  test    al, al
0x18000a282  jz      short loc_18000A2A4
0x18000a284  lea     rdx, __xc_z; Last
0x18000a28b  lea     rcx, __xc_a; First
0x18000a292  call    _initterm_0
0x18000a297  mov     cs:__scrt_current_native_startup_state, 2
0x18000a2a1  xor     dil, dil
0x18000a2a4  mov     cl, bl
0x18000a2a6  call    __scrt_release_startup_lock
0x18000a2ab  test    dil, dil
0x18000a2ae  jnz     short loc_18000A2EA
0x18000a2b0  call    __scrt_get_dyn_tls_init_callback
0x18000a2b5  mov     rbx, rax
0x18000a2b8  cmp     qword ptr [rax], 0
0x18000a2bc  jz      short loc_18000A2DD
0x18000a2be  mov     rcx, rax
0x18000a2c1  call    __scrt_is_nonwritable_in_current_image
0x18000a2c6  test    al, al
0x18000a2c8  jz      short loc_18000A2DD
0x18000a2ca  mov     r8, rsi
0x18000a2cd  mov     edx, 2
0x18000a2d2  mov     rcx, r14
0x18000a2d5  mov     rax, [rbx]
0x18000a2d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2dd  inc     cs:dword_18002DAD0
0x18000a2e3  mov     eax, 1
0x18000a2e8  jmp     short loc_18000A2EC
0x18000a2ea  xor     eax, eax
0x18000a2ec  add     rsp, 28h
0x18000a2f0  pop     r14
0x18000a2f2  pop     rdi
0x18000a2f3  pop     rsi
0x18000a2f4  pop     rbx
0x18000a2f5  retn
0x18000a2f6  mov     ecx, 7
0x18000a2fb  call    __scrt_fastfail
0x18001e948  push    rbp
0x18001e94a  sub     rsp, 20h
0x18001e94e  mov     rbp, rdx
0x18001e951  mov     cl, [rbp+60h]
0x18001e954  add     rsp, 20h
0x18001e958  pop     rbp
0x18001e959  jmp     __scrt_release_startup_lock
```
