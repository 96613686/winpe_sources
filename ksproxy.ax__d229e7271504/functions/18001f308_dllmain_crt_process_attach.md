# dllmain_crt_process_attach

- ea: `0x18001f308`
- end: `0x18001f402`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x18001f2b0`

## callees

- `0x18001f308`
- `0x18001f668`
- `0x18001f6a8`
- `0x18001f6e4`
- `0x18001f7e4`
- `0x18001f8b8`
- `0x18001f958`
- `0x18001fad0`
- `0x18001faf8`
- `0x18001fb1c`
- `0x18001fb2c`
- `0x18001fb38`
- `0x18001fea6`
- `0x18001feb2`
- `0x180045010`

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
  ++dword_180051310;
  return 1;
}

```

## disassembly

```asm
0x18001f308  push    rbx
0x18001f30a  push    rsi
0x18001f30b  push    rdi
0x18001f30c  push    r14
0x18001f30e  sub     rsp, 28h
0x18001f312  mov     rsi, rdx
0x18001f315  mov     r14, rcx
0x18001f318  xor     ecx, ecx
0x18001f31a  call    __scrt_initialize_crt
0x18001f31f  test    al, al
0x18001f321  jz      loc_18001F3EA
0x18001f327  call    __scrt_acquire_startup_lock
0x18001f32c  mov     bl, al
0x18001f32e  mov     [rsp+48h+arg_10], al
0x18001f332  mov     dil, 1
0x18001f335  cmp     cs:__scrt_current_native_startup_state, 0
0x18001f33c  jnz     loc_18001F3F6
0x18001f342  mov     cs:__scrt_current_native_startup_state, 1
0x18001f34c  call    __scrt_dllmain_before_initialize_c
0x18001f351  test    al, al
0x18001f353  jz      short loc_18001F3A4
0x18001f355  call    _RTC_Initialize
0x18001f35a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18001f35f  call    __scrt_initialize_default_local_stdio_options
0x18001f364  lea     rdx, __xi_z; Last
0x18001f36b  lea     rcx, __xi_a; First
0x18001f372  call    _initterm_e_0
0x18001f377  test    eax, eax
0x18001f379  jnz     short loc_18001F3A4
0x18001f37b  call    __scrt_dllmain_after_initialize_c
0x18001f380  test    al, al
0x18001f382  jz      short loc_18001F3A4
0x18001f384  lea     rdx, __xc_z; Last
0x18001f38b  lea     rcx, __xc_a; First
0x18001f392  call    _initterm_0
0x18001f397  mov     cs:__scrt_current_native_startup_state, 2
0x18001f3a1  xor     dil, dil
0x18001f3a4  mov     cl, bl
0x18001f3a6  call    __scrt_release_startup_lock
0x18001f3ab  test    dil, dil
0x18001f3ae  jnz     short loc_18001F3EA
0x18001f3b0  call    __scrt_get_dyn_tls_init_callback
0x18001f3b5  mov     rbx, rax
0x18001f3b8  cmp     qword ptr [rax], 0
0x18001f3bc  jz      short loc_18001F3DD
0x18001f3be  mov     rcx, rax
0x18001f3c1  call    __scrt_is_nonwritable_in_current_image
0x18001f3c6  test    al, al
0x18001f3c8  jz      short loc_18001F3DD
0x18001f3ca  mov     r8, rsi
0x18001f3cd  mov     edx, 2
0x18001f3d2  mov     rcx, r14
0x18001f3d5  mov     rax, [rbx]
0x18001f3d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3dd  inc     cs:dword_180051310
0x18001f3e3  mov     eax, 1
0x18001f3e8  jmp     short loc_18001F3EC
0x18001f3ea  xor     eax, eax
0x18001f3ec  add     rsp, 28h
0x18001f3f0  pop     r14
0x18001f3f2  pop     rdi
0x18001f3f3  pop     rsi
0x18001f3f4  pop     rbx
0x18001f3f5  retn
0x18001f3f6  mov     ecx, 7
0x18001f3fb  call    __scrt_fastfail
0x1800448dc  push    rbp
0x1800448de  sub     rsp, 20h
0x1800448e2  mov     rbp, rdx
0x1800448e5  mov     cl, [rbp+60h]
0x1800448e8  add     rsp, 20h
0x1800448ec  pop     rbp
0x1800448ed  jmp     __scrt_release_startup_lock
```
