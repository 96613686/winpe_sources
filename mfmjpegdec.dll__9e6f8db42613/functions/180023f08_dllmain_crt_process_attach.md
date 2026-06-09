# dllmain_crt_process_attach

- ea: `0x180023f08`
- end: `0x180024002`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180023eb0`

## callees

- `0x180023f08`
- `0x180024244`
- `0x180024284`
- `0x1800242c0`
- `0x1800243c0`
- `0x180024494`
- `0x180024534`
- `0x1800246b8`
- `0x1800246e0`
- `0x180024704`
- `0x180024714`
- `0x180024720`
- `0x180024a96`
- `0x180024aa2`
- `0x180070010`

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
  ++dword_18009CC10;
  return 1;
}

```

## disassembly

```asm
0x180023f08  push    rbx
0x180023f0a  push    rsi
0x180023f0b  push    rdi
0x180023f0c  push    r14
0x180023f0e  sub     rsp, 28h
0x180023f12  mov     rsi, rdx
0x180023f15  mov     r14, rcx
0x180023f18  xor     ecx, ecx
0x180023f1a  call    __scrt_initialize_crt
0x180023f1f  test    al, al
0x180023f21  jz      loc_180023FEA
0x180023f27  call    __scrt_acquire_startup_lock
0x180023f2c  mov     bl, al
0x180023f2e  mov     [rsp+48h+arg_10], al
0x180023f32  mov     dil, 1
0x180023f35  cmp     cs:__scrt_current_native_startup_state, 0
0x180023f3c  jnz     loc_180023FF6
0x180023f42  mov     cs:__scrt_current_native_startup_state, 1
0x180023f4c  call    __scrt_dllmain_before_initialize_c
0x180023f51  test    al, al
0x180023f53  jz      short loc_180023FA4
0x180023f55  call    _RTC_Initialize
0x180023f5a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180023f5f  call    __scrt_initialize_default_local_stdio_options
0x180023f64  lea     rdx, __xi_z; Last
0x180023f6b  lea     rcx, __xi_a; First
0x180023f72  call    _initterm_e_0
0x180023f77  test    eax, eax
0x180023f79  jnz     short loc_180023FA4
0x180023f7b  call    __scrt_dllmain_after_initialize_c
0x180023f80  test    al, al
0x180023f82  jz      short loc_180023FA4
0x180023f84  lea     rdx, __xc_z; Last
0x180023f8b  lea     rcx, __xc_a; First
0x180023f92  call    _initterm_0
0x180023f97  mov     cs:__scrt_current_native_startup_state, 2
0x180023fa1  xor     dil, dil
0x180023fa4  mov     cl, bl
0x180023fa6  call    __scrt_release_startup_lock
0x180023fab  test    dil, dil
0x180023fae  jnz     short loc_180023FEA
0x180023fb0  call    __scrt_get_dyn_tls_init_callback
0x180023fb5  mov     rbx, rax
0x180023fb8  cmp     qword ptr [rax], 0
0x180023fbc  jz      short loc_180023FDD
0x180023fbe  mov     rcx, rax
0x180023fc1  call    __scrt_is_nonwritable_in_current_image
0x180023fc6  test    al, al
0x180023fc8  jz      short loc_180023FDD
0x180023fca  mov     r8, rsi
0x180023fcd  mov     edx, 2
0x180023fd2  mov     rcx, r14
0x180023fd5  mov     rax, [rbx]
0x180023fd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023fdd  inc     cs:dword_18009CC10
0x180023fe3  mov     eax, 1
0x180023fe8  jmp     short loc_180023FEC
0x180023fea  xor     eax, eax
0x180023fec  add     rsp, 28h
0x180023ff0  pop     r14
0x180023ff2  pop     rdi
0x180023ff3  pop     rsi
0x180023ff4  pop     rbx
0x180023ff5  retn
0x180023ff6  mov     ecx, 7
0x180023ffb  call    __scrt_fastfail
0x18006f09a  push    rbp
0x18006f09c  sub     rsp, 20h
0x18006f0a0  mov     rbp, rdx
0x18006f0a3  mov     cl, [rbp+60h]
0x18006f0a6  add     rsp, 20h
0x18006f0aa  pop     rbp
0x18006f0ab  jmp     __scrt_release_startup_lock
```
