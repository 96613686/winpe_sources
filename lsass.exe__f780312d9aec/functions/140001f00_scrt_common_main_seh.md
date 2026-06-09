# __scrt_common_main_seh

- ea: `0x140001f00`
- end: `0x14000207b`
- name: `__scrt_common_main_seh`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x140002090`

## callees

- `0x140001f00`
- `0x1400020e4`
- `0x140002124`
- `0x1400021f8`
- `0x140002298`
- `0x1400022c4`
- `0x140002470`
- `0x140002480`
- `0x140002490`
- `0x1400024a8`
- `0x1400028d6`
- `0x1400028e2`
- `0x1400028ee`
- `0x1400028fa`
- `0x140002906`
- `0x140002912`
- `0x14000292a`
- `0x14000295a`
- `0x140002966`
- `0x140002996`
- `0x1400029c6`
- `0x1400031bc`
- `0x140006010`

## pseudocode

```c
__int64 _scrt_common_main_seh()
{
  __int64 v0; // rcx
  char v1; // bl
  __int64 v2; // rcx
  __int64 v4; // rcx
  _QWORD *dyn_tls_init_callback; // rax
  __int64 v6; // rcx
  void (__fastcall **v7)(_QWORD, __int64); // rbx
  _tls_callback_type *dyn_tls_dtor_callback; // rax
  _tls_callback_type *v9; // rbx

  if ( !(unsigned __int8)_scrt_initialize_crt(1) )
    _scrt_fastfail(7);
  v1 = _scrt_acquire_startup_lock(v0);
  v2 = (unsigned int)_scrt_current_native_startup_state;
  if ( _scrt_current_native_startup_state == 1 )
    _scrt_fastfail(7);
  if ( _scrt_current_native_startup_state )
  {
LABEL_7:
    LOBYTE(v2) = v1;
    _scrt_release_startup_lock(v2);
    dyn_tls_init_callback = (_QWORD *)_scrt_get_dyn_tls_init_callback(v4);
    v7 = (void (__fastcall **)(_QWORD, __int64))dyn_tls_init_callback;
    if ( *dyn_tls_init_callback && (unsigned __int8)_scrt_is_nonwritable_in_current_image(dyn_tls_init_callback) )
      (*v7)(0, 2);
    dyn_tls_dtor_callback = (_tls_callback_type *)_scrt_get_dyn_tls_dtor_callback(v6);
    v9 = dyn_tls_dtor_callback;
    if ( *dyn_tls_dtor_callback && (unsigned __int8)_scrt_is_nonwritable_in_current_image(dyn_tls_dtor_callback) )
      register_thread_local_exe_atexit_callback_0(*v9);
    get_initial_wide_environment();
    _p___wargv();
    _p___argc();
    wmain();
  }
  _scrt_current_native_startup_state = 1;
  if ( !initterm_e_0((_PIFV *)&_xi_a, (_PIFV *)&_xi_z) )
  {
    initterm_0((_PVFV *)&_xc_a, (_PVFV *)&_xc_z);
    _scrt_current_native_startup_state = 2;
    goto LABEL_7;
  }
  return 255;
}

```

## disassembly

```asm
0x140001f00  mov     [rsp+arg_0], rbx
0x140001f05  mov     [rsp+arg_8], rsi
0x140001f0a  push    rdi
0x140001f0b  sub     rsp, 30h
0x140001f0f  mov     ecx, 1
0x140001f14  call    __scrt_initialize_crt
0x140001f19  test    al, al
0x140001f1b  jz      loc_140002056
0x140001f21  xor     sil, sil
0x140001f24  mov     [rsp+38h+var_18], sil
0x140001f29  call    __scrt_acquire_startup_lock
0x140001f2e  mov     bl, al
0x140001f30  mov     ecx, cs:__scrt_current_native_startup_state
0x140001f36  cmp     ecx, 1
0x140001f39  jz      loc_140002061
0x140001f3f  test    ecx, ecx
0x140001f41  jnz     short loc_140001F8D
0x140001f43  mov     cs:__scrt_current_native_startup_state, 1
0x140001f4d  lea     rdx, __xi_z; Last
0x140001f54  lea     rcx, __xi_a; First
0x140001f5b  call    _initterm_e_0
0x140001f60  test    eax, eax
0x140001f62  jz      short loc_140001F6E
0x140001f64  mov     eax, 0FFh
0x140001f69  jmp     loc_140002046
0x140001f6e  lea     rdx, __xc_z; Last
0x140001f75  lea     rcx, __xc_a; First
0x140001f7c  call    _initterm_0
0x140001f81  mov     cs:__scrt_current_native_startup_state, 2
0x140001f8b  jmp     short loc_140001F95
0x140001f8d  mov     sil, 1
0x140001f90  mov     [rsp+38h+var_18], sil
0x140001f95  mov     cl, bl
0x140001f97  call    __scrt_release_startup_lock
0x140001f9c  call    __scrt_get_dyn_tls_init_callback
0x140001fa1  mov     rbx, rax
0x140001fa4  cmp     qword ptr [rax], 0
0x140001fa8  jz      short loc_140001FC7
0x140001faa  mov     rcx, rax
0x140001fad  call    __scrt_is_nonwritable_in_current_image
0x140001fb2  test    al, al
0x140001fb4  jz      short loc_140001FC7
0x140001fb6  xor     r8d, r8d
0x140001fb9  lea     edx, [r8+2]
0x140001fbd  xor     ecx, ecx
0x140001fbf  mov     rax, [rbx]
0x140001fc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001fc7  call    __scrt_get_dyn_tls_dtor_callback
0x140001fcc  mov     rbx, rax
0x140001fcf  cmp     qword ptr [rax], 0
0x140001fd3  jz      short loc_140001FE9
0x140001fd5  mov     rcx, rax
0x140001fd8  call    __scrt_is_nonwritable_in_current_image
0x140001fdd  test    al, al
0x140001fdf  jz      short loc_140001FE9
0x140001fe1  mov     rcx, [rbx]; Callback
0x140001fe4  call    _register_thread_local_exe_atexit_callback_0
0x140001fe9  call    _get_initial_wide_environment
0x140001fee  mov     rdi, rax
0x140001ff1  call    __p___wargv
0x140001ff6  mov     rbx, [rax]
0x140001ff9  call    __p___argc
0x140001ffe  mov     r8, rdi
0x140002001  mov     rdx, rbx
0x140002004  mov     ecx, [rax]
0x140002006  call    wmain
0x14000200b  mov     ebx, eax
0x14000200d  call    __scrt_is_managed_app
0x140002012  test    al, al
0x140002014  jz      short loc_14000206B
0x140002016  test    sil, sil
0x140002019  jnz     short loc_140002020
0x14000201b  call    _o__cexit_0
0x140002020  xor     edx, edx
0x140002022  mov     cl, 1
0x140002024  call    __scrt_uninitialize_crt
0x140002029  mov     eax, ebx
0x14000202b  jmp     short loc_140002046
0x14000202d  mov     ebx, eax
0x14000202f  call    __scrt_is_managed_app
0x140002034  test    al, al
0x140002036  jz      short loc_140002073
0x140002038  cmp     [rsp+38h+var_18], 0
0x14000203d  jnz     short loc_140002044
0x14000203f  call    _c_exit_0
0x140002044  mov     eax, ebx
0x140002046  mov     rbx, [rsp+38h+arg_0]
0x14000204b  mov     rsi, [rsp+38h+arg_8]
0x140002050  add     rsp, 30h
0x140002054  pop     rdi
0x140002055  retn
0x140002056  mov     ecx, 7
0x14000205b  call    __scrt_fastfail
0x140002061  mov     ecx, 7
0x140002066  call    __scrt_fastfail
0x14000206b  mov     ecx, ebx; Code
0x14000206d  call    _o_exit_0
0x140002073  mov     ecx, ebx
0x140002075  call    _o__exit_0
0x14000207a  nop
0x14000530c  push    rbp
0x14000530e  sub     rsp, 20h
0x140005312  mov     rbp, rdx
0x140005315  mov     rdx, rcx; ExceptionPtr
0x140005318  mov     rcx, [rcx]
0x14000531b  mov     ecx, [rcx]; ExceptionNum
0x14000531d  call    _seh_filter_exe
0x140005322  nop
0x140005323  add     rsp, 20h
0x140005327  pop     rbp
0x140005328  retn
```
