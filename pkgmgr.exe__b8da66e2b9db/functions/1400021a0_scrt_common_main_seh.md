# __scrt_common_main_seh

- ea: `0x1400021a0`
- end: `0x14000231b`
- name: `__scrt_common_main_seh`
- size: `379`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x140002330`

## callees

- `0x1400021a0`
- `0x140002384`
- `0x1400023c4`
- `0x140002498`
- `0x140002538`
- `0x140002564`
- `0x140002744`
- `0x140002754`
- `0x140002764`
- `0x14000277c`
- `0x140002bb6`
- `0x140002bc2`
- `0x140002bce`
- `0x140002bda`
- `0x140002bf2`
- `0x140002bfe`
- `0x140002c5e`
- `0x140002c9a`
- `0x140002cb2`
- `0x140002d08`
- `0x140002d38`
- `0x14000d734`
- `0x14002a010`

## pseudocode

```c
__int64 _scrt_common_main_seh()
{
  __int64 v0; // rcx
  char v1; // si
  char v2; // bl
  __int64 v3; // rcx
  __int64 v5; // rcx
  _QWORD *dyn_tls_init_callback; // rax
  __int64 v7; // rcx
  void (__fastcall **v8)(_QWORD, __int64); // rbx
  _tls_callback_type *dyn_tls_dtor_callback; // rax
  _tls_callback_type *v10; // rbx
  wchar_t **v11; // rbx
  int *v12; // rax
  unsigned int v13; // ebx
  __int64 v14; // rcx
  __int64 v15; // rcx

  if ( !(unsigned __int8)_scrt_initialize_crt(1) )
    _scrt_fastfail(7);
  v1 = 0;
  v2 = _scrt_acquire_startup_lock(v0);
  v3 = (unsigned int)_scrt_current_native_startup_state;
  if ( _scrt_current_native_startup_state == 1 )
    _scrt_fastfail(7);
  if ( _scrt_current_native_startup_state )
  {
    v1 = 1;
  }
  else
  {
    _scrt_current_native_startup_state = 1;
    if ( initterm_e_0((_PIFV *)&_xi_a, (_PIFV *)&_xi_z) )
      return 255;
    initterm_0((_PVFV *)&_xc_a, (_PVFV *)&_xc_z);
    _scrt_current_native_startup_state = 2;
  }
  LOBYTE(v3) = v2;
  _scrt_release_startup_lock(v3);
  dyn_tls_init_callback = (_QWORD *)_scrt_get_dyn_tls_init_callback(v5);
  v8 = (void (__fastcall **)(_QWORD, __int64))dyn_tls_init_callback;
  if ( *dyn_tls_init_callback && (unsigned __int8)_scrt_is_nonwritable_in_current_image(dyn_tls_init_callback) )
    (*v8)(0, 2);
  dyn_tls_dtor_callback = (_tls_callback_type *)_scrt_get_dyn_tls_dtor_callback(v7);
  v10 = dyn_tls_dtor_callback;
  if ( *dyn_tls_dtor_callback && (unsigned __int8)_scrt_is_nonwritable_in_current_image(dyn_tls_dtor_callback) )
    register_thread_local_exe_atexit_callback_0(*v10);
  get_initial_wide_environment();
  v11 = *_p___wargv();
  v12 = _p___argc();
  v13 = wmain(*v12, (__int64)v11);
  if ( !(unsigned __int8)_scrt_is_managed_app(v14) )
    o_exit_0(v13);
  if ( !v1 )
    o__cexit_0(v15);
  LOBYTE(v15) = 1;
  _scrt_uninitialize_crt(v15, 0);
  return v13;
}

```

## disassembly

```asm
0x1400021a0  mov     [rsp+arg_0], rbx
0x1400021a5  mov     [rsp+arg_8], rsi
0x1400021aa  push    rdi
0x1400021ab  sub     rsp, 30h
0x1400021af  mov     ecx, 1
0x1400021b4  call    __scrt_initialize_crt
0x1400021b9  test    al, al
0x1400021bb  jz      loc_1400022F6
0x1400021c1  xor     sil, sil
0x1400021c4  mov     [rsp+38h+var_18], sil
0x1400021c9  call    __scrt_acquire_startup_lock
0x1400021ce  mov     bl, al
0x1400021d0  mov     ecx, cs:__scrt_current_native_startup_state
0x1400021d6  cmp     ecx, 1
0x1400021d9  jz      loc_140002301
0x1400021df  test    ecx, ecx
0x1400021e1  jnz     short loc_14000222D
0x1400021e3  mov     cs:__scrt_current_native_startup_state, 1
0x1400021ed  lea     rdx, __xi_z; Last
0x1400021f4  lea     rcx, __xi_a; First
0x1400021fb  call    _initterm_e_0
0x140002200  test    eax, eax
0x140002202  jz      short loc_14000220E
0x140002204  mov     eax, 0FFh
0x140002209  jmp     loc_1400022E6
0x14000220e  lea     rdx, __xc_z; Last
0x140002215  lea     rcx, __xc_a; First
0x14000221c  call    _initterm_0
0x140002221  mov     cs:__scrt_current_native_startup_state, 2
0x14000222b  jmp     short loc_140002235
0x14000222d  mov     sil, 1
0x140002230  mov     [rsp+38h+var_18], sil
0x140002235  mov     cl, bl
0x140002237  call    __scrt_release_startup_lock
0x14000223c  call    __scrt_get_dyn_tls_init_callback
0x140002241  mov     rbx, rax
0x140002244  cmp     qword ptr [rax], 0
0x140002248  jz      short loc_140002267
0x14000224a  mov     rcx, rax
0x14000224d  call    __scrt_is_nonwritable_in_current_image
0x140002252  test    al, al
0x140002254  jz      short loc_140002267
0x140002256  xor     r8d, r8d
0x140002259  lea     edx, [r8+2]
0x14000225d  xor     ecx, ecx
0x14000225f  mov     rax, [rbx]
0x140002262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002267  call    __scrt_get_dyn_tls_dtor_callback
0x14000226c  mov     rbx, rax
0x14000226f  cmp     qword ptr [rax], 0
0x140002273  jz      short loc_140002289
0x140002275  mov     rcx, rax
0x140002278  call    __scrt_is_nonwritable_in_current_image
0x14000227d  test    al, al
0x14000227f  jz      short loc_140002289
0x140002281  mov     rcx, [rbx]; Callback
0x140002284  call    _register_thread_local_exe_atexit_callback_0
0x140002289  call    _get_initial_wide_environment
0x14000228e  mov     rdi, rax
0x140002291  call    __p___wargv
0x140002296  mov     rbx, [rax]
0x140002299  call    __p___argc
0x14000229e  mov     r8, rdi
0x1400022a1  mov     rdx, rbx
0x1400022a4  mov     ecx, [rax]
0x1400022a6  call    wmain
0x1400022ab  mov     ebx, eax
0x1400022ad  call    __scrt_is_managed_app
0x1400022b2  test    al, al
0x1400022b4  jz      short loc_14000230B
0x1400022b6  test    sil, sil
0x1400022b9  jnz     short loc_1400022C0
0x1400022bb  call    _o__cexit_0
0x1400022c0  xor     edx, edx
0x1400022c2  mov     cl, 1
0x1400022c4  call    __scrt_uninitialize_crt
0x1400022c9  mov     eax, ebx
0x1400022cb  jmp     short loc_1400022E6
0x1400022cd  mov     ebx, eax
0x1400022cf  call    __scrt_is_managed_app
0x1400022d4  test    al, al
0x1400022d6  jz      short loc_140002313
0x1400022d8  cmp     [rsp+38h+var_18], 0
0x1400022dd  jnz     short loc_1400022E4
0x1400022df  call    _c_exit_0
0x1400022e4  mov     eax, ebx
0x1400022e6  mov     rbx, [rsp+38h+arg_0]
0x1400022eb  mov     rsi, [rsp+38h+arg_8]
0x1400022f0  add     rsp, 30h
0x1400022f4  pop     rdi
0x1400022f5  retn
0x1400022f6  mov     ecx, 7
0x1400022fb  call    __scrt_fastfail
0x140002301  mov     ecx, 7
0x140002306  call    __scrt_fastfail
0x14000230b  mov     ecx, ebx; Code
0x14000230d  call    _o_exit_0
0x140002313  mov     ecx, ebx
0x140002315  call    _o__exit_0
0x14000231a  nop
0x140029c7c  push    rbp
0x140029c7e  sub     rsp, 20h
0x140029c82  mov     rbp, rdx
0x140029c85  mov     rdx, rcx; ExceptionPtr
0x140029c88  mov     rcx, [rcx]
0x140029c8b  mov     ecx, [rcx]; ExceptionNum
0x140029c8d  call    _seh_filter_exe
0x140029c92  nop
0x140029c93  add     rsp, 20h
0x140029c97  pop     rbp
0x140029c98  retn
```
