# __scrt_common_main_seh

- ea: `0x14001304c`
- end: `0x1400131c8`
- name: `__scrt_common_main_seh`
- size: `380`
- prototype: `__int64 __fastcall()`
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x1400131d0`

## callees

- `0x140009c08`
- `0x14001304c`
- `0x1400134c8`
- `0x140013504`
- `0x1400135dc`
- `0x140013674`
- `0x140013698`
- `0x140013854`
- `0x14001385c`
- `0x14001386c`
- `0x1400139c0`
- `0x140013cee`
- `0x140013cf4`
- `0x140013d12`
- `0x140013d18`
- `0x140013d1e`
- `0x140013d24`
- `0x140013d30`
- `0x140013d36`
- `0x140013d3c`
- `0x140013d42`
- `0x140013d48`
- `0x140013f30`

## pseudocode

```c
__int64 __fastcall _scrt_common_main_seh()
{
  unsigned int v0; // ebx
  __int64 v1; // rcx
  char v2; // si
  __int64 v3; // rcx
  __int64 v5; // rcx
  _QWORD *dyn_tls_init_callback; // rax
  __int64 v7; // rcx
  void (__fastcall **v8)(_QWORD, __int64); // rbx
  _tls_callback_type *dyn_tls_dtor_callback; // rax
  _tls_callback_type *v10; // rbx
  wchar_t **initial_wide_environment_0; // rdi
  wchar_t **v12; // rbx
  int *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rcx

  if ( !(unsigned __int8)_scrt_initialize_crt(1) )
  {
    _scrt_fastfail(7);
    goto LABEL_19;
  }
  v2 = 0;
  LOBYTE(v0) = _scrt_acquire_startup_lock(v1);
  v3 = (unsigned int)_scrt_current_native_startup_state;
  if ( _scrt_current_native_startup_state == 1 )
  {
LABEL_19:
    _scrt_fastfail(7);
    goto LABEL_20;
  }
  if ( _scrt_current_native_startup_state )
  {
    v2 = 1;
  }
  else
  {
    _scrt_current_native_startup_state = 1;
    if ( initterm_e_0((_PIFV *)&_xi_a, (_PIFV *)&_xi_z) )
      return 255;
    initterm_0((_PVFV *)&_xc_a, (_PVFV *)&_xc_z);
    _scrt_current_native_startup_state = 2;
  }
  LOBYTE(v3) = v0;
  _scrt_release_startup_lock(v3);
  dyn_tls_init_callback = (_QWORD *)_scrt_get_dyn_tls_init_callback(v5);
  v8 = (void (__fastcall **)(_QWORD, __int64))dyn_tls_init_callback;
  if ( *dyn_tls_init_callback && (unsigned __int8)_scrt_is_nonwritable_in_current_image(dyn_tls_init_callback) )
    (*v8)(0, 2);
  dyn_tls_dtor_callback = (_tls_callback_type *)_scrt_get_dyn_tls_dtor_callback(v7);
  v10 = dyn_tls_dtor_callback;
  if ( *dyn_tls_dtor_callback && (unsigned __int8)_scrt_is_nonwritable_in_current_image(dyn_tls_dtor_callback) )
    register_thread_local_exe_atexit_callback_0(*v10);
  initial_wide_environment_0 = get_initial_wide_environment_0();
  v12 = *_p___wargv_0();
  v13 = _p___argc_0();
  v0 = main(*v13, (const char **)v12, (const char **)initial_wide_environment_0);
  if ( !(unsigned __int8)_scrt_is_managed_app(v14) )
LABEL_20:
    exit_0(v0);
  if ( !v2 )
    cexit_0();
  LOBYTE(v15) = 1;
  _scrt_uninitialize_crt(v15, 0);
  return v0;
}

```

## disassembly

```asm
0x14001304c  mov     [rsp+arg_0], rbx
0x140013051  mov     [rsp+arg_8], rsi
0x140013056  push    rdi
0x140013057  sub     rsp, 30h
0x14001305b  mov     ecx, 1
0x140013060  call    __scrt_initialize_crt
0x140013065  test    al, al
0x140013067  jz      loc_1400131A3
0x14001306d  xor     sil, sil
0x140013070  mov     [rsp+38h+var_18], sil
0x140013075  call    __scrt_acquire_startup_lock
0x14001307a  mov     bl, al
0x14001307c  mov     ecx, cs:__scrt_current_native_startup_state
0x140013082  cmp     ecx, 1
0x140013085  jz      loc_1400131AE
0x14001308b  test    ecx, ecx
0x14001308d  jnz     short loc_1400130D9
0x14001308f  mov     cs:__scrt_current_native_startup_state, 1
0x140013099  lea     rdx, __xi_z; Last
0x1400130a0  lea     rcx, __xi_a; First
0x1400130a7  call    _initterm_e_0
0x1400130ac  test    eax, eax
0x1400130ae  jz      short loc_1400130BA
0x1400130b0  mov     eax, 0FFh
0x1400130b5  jmp     loc_140013193
0x1400130ba  lea     rdx, __xc_z; Last
0x1400130c1  lea     rcx, __xc_a; First
0x1400130c8  call    _initterm_0
0x1400130cd  mov     cs:__scrt_current_native_startup_state, 2
0x1400130d7  jmp     short loc_1400130E1
0x1400130d9  mov     sil, 1
0x1400130dc  mov     [rsp+38h+var_18], sil
0x1400130e1  mov     cl, bl
0x1400130e3  call    __scrt_release_startup_lock
0x1400130e8  call    __scrt_get_dyn_tls_init_callback
0x1400130ed  mov     rbx, rax
0x1400130f0  cmp     qword ptr [rax], 0
0x1400130f4  jz      short loc_140013114
0x1400130f6  mov     rcx, rax
0x1400130f9  call    __scrt_is_nonwritable_in_current_image
0x1400130fe  test    al, al
0x140013100  jz      short loc_140013114
0x140013102  xor     r8d, r8d
0x140013105  lea     edx, [r8+2]
0x140013109  xor     ecx, ecx
0x14001310b  mov     rax, [rbx]
0x14001310e  call    cs:__guard_dispatch_icall_fptr
0x140013114  call    __scrt_get_dyn_tls_dtor_callback
0x140013119  mov     rbx, rax
0x14001311c  cmp     qword ptr [rax], 0
0x140013120  jz      short loc_140013136
0x140013122  mov     rcx, rax
0x140013125  call    __scrt_is_nonwritable_in_current_image
0x14001312a  test    al, al
0x14001312c  jz      short loc_140013136
0x14001312e  mov     rcx, [rbx]; Callback
0x140013131  call    _register_thread_local_exe_atexit_callback_0
0x140013136  call    _get_initial_wide_environment_0
0x14001313b  mov     rdi, rax
0x14001313e  call    __p___wargv_0
0x140013143  mov     rbx, [rax]
0x140013146  call    __p___argc_0
0x14001314b  mov     r8, rdi; envp
0x14001314e  mov     rdx, rbx; argv
0x140013151  mov     ecx, [rax]; argc
0x140013153  call    main
0x140013158  mov     ebx, eax
0x14001315a  call    __scrt_is_managed_app
0x14001315f  test    al, al
0x140013161  jz      short loc_1400131B8
0x140013163  test    sil, sil
0x140013166  jnz     short loc_14001316D
0x140013168  call    _cexit_0
0x14001316d  xor     edx, edx
0x14001316f  mov     cl, 1
0x140013171  call    __scrt_uninitialize_crt
0x140013176  mov     eax, ebx
0x140013178  jmp     short loc_140013193
0x14001317a  mov     ebx, eax
0x14001317c  call    __scrt_is_managed_app
0x140013181  test    al, al
0x140013183  jz      short loc_1400131C0
0x140013185  cmp     [rsp+38h+var_18], 0
0x14001318a  jnz     short loc_140013191
0x14001318c  call    _c_exit_0
0x140013191  mov     eax, ebx
0x140013193  mov     rbx, [rsp+38h+arg_0]
0x140013198  mov     rsi, [rsp+38h+arg_8]
0x14001319d  add     rsp, 30h
0x1400131a1  pop     rdi
0x1400131a2  retn
0x1400131a3  mov     ecx, 7
0x1400131a8  call    __scrt_fastfail
0x1400131ad  nop
0x1400131ae  mov     ecx, 7
0x1400131b3  call    __scrt_fastfail
0x1400131b8  mov     ecx, ebx; Code
0x1400131ba  call    exit_0
0x1400131c0  mov     ecx, ebx; Code
0x1400131c2  call    _exit_0
0x140015ec5  push    rbp
0x140015ec7  sub     rsp, 20h
0x140015ecb  mov     rbp, rdx
0x140015ece  mov     rax, [rcx]
0x140015ed1  mov     rdx, rcx; ExceptionPtr
0x140015ed4  mov     ecx, [rax]; ExceptionNum
0x140015ed6  call    _seh_filter_exe_0
0x140015edb  nop
0x140015edc  add     rsp, 20h
0x140015ee0  pop     rbp
0x140015ee1  retn
```
