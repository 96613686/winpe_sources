# __scrt_common_main_seh

- ea: `0x140001180`
- end: `0x1400012fb`
- name: `__scrt_common_main_seh`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x140001310`

## callees

- `0x140001180`
- `0x140001364`
- `0x1400013a4`
- `0x140001478`
- `0x140001518`
- `0x140001544`
- `0x140001710`
- `0x140001720`
- `0x140001730`
- `0x140001748`
- `0x140001b76`
- `0x140001b82`
- `0x140001b8e`
- `0x140001b9a`
- `0x140001ba6`
- `0x140001bb2`
- `0x140001bca`
- `0x140001bfa`
- `0x140001c06`
- `0x140001c36`
- `0x140001c66`
- `0x140001ca4`
- `0x140002010`

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
0x140001180  mov     [rsp+arg_0], rbx
0x140001185  mov     [rsp+arg_8], rsi
0x14000118a  push    rdi
0x14000118b  sub     rsp, 30h
0x14000118f  mov     ecx, 1
0x140001194  call    __scrt_initialize_crt
0x140001199  test    al, al
0x14000119b  jz      loc_1400012D6
0x1400011a1  xor     sil, sil
0x1400011a4  mov     [rsp+38h+var_18], sil
0x1400011a9  call    __scrt_acquire_startup_lock
0x1400011ae  mov     bl, al
0x1400011b0  mov     ecx, cs:__scrt_current_native_startup_state
0x1400011b6  cmp     ecx, 1
0x1400011b9  jz      loc_1400012E1
0x1400011bf  test    ecx, ecx
0x1400011c1  jnz     short loc_14000120D
0x1400011c3  mov     cs:__scrt_current_native_startup_state, 1
0x1400011cd  lea     rdx, __xi_z; Last
0x1400011d4  lea     rcx, __xi_a; First
0x1400011db  call    _initterm_e_0
0x1400011e0  test    eax, eax
0x1400011e2  jz      short loc_1400011EE
0x1400011e4  mov     eax, 0FFh
0x1400011e9  jmp     loc_1400012C6
0x1400011ee  lea     rdx, __xc_z; Last
0x1400011f5  lea     rcx, __xc_a; First
0x1400011fc  call    _initterm_0
0x140001201  mov     cs:__scrt_current_native_startup_state, 2
0x14000120b  jmp     short loc_140001215
0x14000120d  mov     sil, 1
0x140001210  mov     [rsp+38h+var_18], sil
0x140001215  mov     cl, bl
0x140001217  call    __scrt_release_startup_lock
0x14000121c  call    __scrt_get_dyn_tls_init_callback
0x140001221  mov     rbx, rax
0x140001224  cmp     qword ptr [rax], 0
0x140001228  jz      short loc_140001247
0x14000122a  mov     rcx, rax
0x14000122d  call    __scrt_is_nonwritable_in_current_image
0x140001232  test    al, al
0x140001234  jz      short loc_140001247
0x140001236  xor     r8d, r8d
0x140001239  lea     edx, [r8+2]
0x14000123d  xor     ecx, ecx
0x14000123f  mov     rax, [rbx]
0x140001242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001247  call    __scrt_get_dyn_tls_dtor_callback
0x14000124c  mov     rbx, rax
0x14000124f  cmp     qword ptr [rax], 0
0x140001253  jz      short loc_140001269
0x140001255  mov     rcx, rax
0x140001258  call    __scrt_is_nonwritable_in_current_image
0x14000125d  test    al, al
0x14000125f  jz      short loc_140001269
0x140001261  mov     rcx, [rbx]; Callback
0x140001264  call    _register_thread_local_exe_atexit_callback_0
0x140001269  call    _get_initial_wide_environment
0x14000126e  mov     rdi, rax
0x140001271  call    __p___wargv
0x140001276  mov     rbx, [rax]
0x140001279  call    __p___argc
0x14000127e  mov     r8, rdi
0x140001281  mov     rdx, rbx
0x140001284  mov     ecx, [rax]
0x140001286  call    wmain
0x14000128b  mov     ebx, eax
0x14000128d  call    __scrt_is_managed_app
0x140001292  test    al, al
0x140001294  jz      short loc_1400012EB
0x140001296  test    sil, sil
0x140001299  jnz     short loc_1400012A0
0x14000129b  call    _o__cexit_0
0x1400012a0  xor     edx, edx
0x1400012a2  mov     cl, 1
0x1400012a4  call    __scrt_uninitialize_crt
0x1400012a9  mov     eax, ebx
0x1400012ab  jmp     short loc_1400012C6
0x1400012ad  mov     ebx, eax
0x1400012af  call    __scrt_is_managed_app
0x1400012b4  test    al, al
0x1400012b6  jz      short loc_1400012F3
0x1400012b8  cmp     [rsp+38h+var_18], 0
0x1400012bd  jnz     short loc_1400012C4
0x1400012bf  call    _c_exit_0
0x1400012c4  mov     eax, ebx
0x1400012c6  mov     rbx, [rsp+38h+arg_0]
0x1400012cb  mov     rsi, [rsp+38h+arg_8]
0x1400012d0  add     rsp, 30h
0x1400012d4  pop     rdi
0x1400012d5  retn
0x1400012d6  mov     ecx, 7
0x1400012db  call    __scrt_fastfail
0x1400012e1  mov     ecx, 7
0x1400012e6  call    __scrt_fastfail
0x1400012eb  mov     ecx, ebx; Code
0x1400012ed  call    _o_exit_0
0x1400012f3  mov     ecx, ebx
0x1400012f5  call    _o__exit_0
0x1400012fa  nop
0x140001d3c  push    rbp
0x140001d3e  sub     rsp, 20h
0x140001d42  mov     rbp, rdx
0x140001d45  mov     rdx, rcx; ExceptionPtr
0x140001d48  mov     rcx, [rcx]
0x140001d4b  mov     ecx, [rcx]; ExceptionNum
0x140001d4d  call    _seh_filter_exe
0x140001d52  nop
0x140001d53  add     rsp, 20h
0x140001d57  pop     rbp
0x140001d58  retn
```
