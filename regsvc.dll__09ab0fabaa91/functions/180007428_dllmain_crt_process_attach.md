# dllmain_crt_process_attach

- ea: `0x180007428`
- end: `0x180007522`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800073d0`

## callees

- `0x180007428`
- `0x180007820`
- `0x180007848`
- `0x18000786c`
- `0x1800078ac`
- `0x1800078e8`
- `0x1800079e8`
- `0x180007abc`
- `0x180007b5c`
- `0x180007bb8`
- `0x180007bc8`
- `0x180007bd4`
- `0x180007f46`
- `0x180007f52`
- `0x18001f010`

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
  ++dword_18002B4D0;
  return 1;
}

```

## disassembly

```asm
0x180007428  push    rbx
0x18000742a  push    rsi
0x18000742b  push    rdi
0x18000742c  push    r14
0x18000742e  sub     rsp, 28h
0x180007432  mov     rsi, rdx
0x180007435  mov     r14, rcx
0x180007438  xor     ecx, ecx
0x18000743a  call    __scrt_initialize_crt
0x18000743f  test    al, al
0x180007441  jz      loc_18000750A
0x180007447  call    __scrt_acquire_startup_lock
0x18000744c  mov     bl, al
0x18000744e  mov     [rsp+48h+arg_10], al
0x180007452  mov     dil, 1
0x180007455  cmp     cs:__scrt_current_native_startup_state, 0
0x18000745c  jnz     loc_180007516
0x180007462  mov     cs:__scrt_current_native_startup_state, 1
0x18000746c  call    __scrt_dllmain_before_initialize_c
0x180007471  test    al, al
0x180007473  jz      short loc_1800074C4
0x180007475  call    _RTC_Initialize
0x18000747a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000747f  call    __scrt_initialize_default_local_stdio_options
0x180007484  lea     rdx, __xi_z; Last
0x18000748b  lea     rcx, __xi_a; First
0x180007492  call    _initterm_e_0
0x180007497  test    eax, eax
0x180007499  jnz     short loc_1800074C4
0x18000749b  call    __scrt_dllmain_after_initialize_c
0x1800074a0  test    al, al
0x1800074a2  jz      short loc_1800074C4
0x1800074a4  lea     rdx, __xc_z; Last
0x1800074ab  lea     rcx, __xc_a; First
0x1800074b2  call    _initterm_0
0x1800074b7  mov     cs:__scrt_current_native_startup_state, 2
0x1800074c1  xor     dil, dil
0x1800074c4  mov     cl, bl
0x1800074c6  call    __scrt_release_startup_lock
0x1800074cb  test    dil, dil
0x1800074ce  jnz     short loc_18000750A
0x1800074d0  call    __scrt_get_dyn_tls_init_callback
0x1800074d5  mov     rbx, rax
0x1800074d8  cmp     qword ptr [rax], 0
0x1800074dc  jz      short loc_1800074FD
0x1800074de  mov     rcx, rax
0x1800074e1  call    __scrt_is_nonwritable_in_current_image
0x1800074e6  test    al, al
0x1800074e8  jz      short loc_1800074FD
0x1800074ea  mov     r8, rsi
0x1800074ed  mov     edx, 2
0x1800074f2  mov     rcx, r14
0x1800074f5  mov     rax, [rbx]
0x1800074f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074fd  inc     cs:dword_18002B4D0
0x180007503  mov     eax, 1
0x180007508  jmp     short loc_18000750C
0x18000750a  xor     eax, eax
0x18000750c  add     rsp, 28h
0x180007510  pop     r14
0x180007512  pop     rdi
0x180007513  pop     rsi
0x180007514  pop     rbx
0x180007515  retn
0x180007516  mov     ecx, 7
0x18000751b  call    __scrt_fastfail
0x18001e4bc  push    rbp
0x18001e4be  sub     rsp, 20h
0x18001e4c2  mov     rbp, rdx
0x18001e4c5  mov     cl, [rbp+60h]
0x18001e4c8  add     rsp, 20h
0x18001e4cc  pop     rbp
0x18001e4cd  jmp     __scrt_release_startup_lock
```
