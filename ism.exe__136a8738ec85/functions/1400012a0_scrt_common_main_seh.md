# __scrt_common_main_seh

- ea: `0x1400012a0`
- end: `0x14000141b`
- name: `__scrt_common_main_seh`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x140001430`

## callees

- `0x1400012a0`
- `0x1400014bc`
- `0x1400014fc`
- `0x1400015d0`
- `0x140001670`
- `0x14000169c`
- `0x140001860`
- `0x140001870`
- `0x140001880`
- `0x140001898`
- `0x140001cd6`
- `0x140001ce2`
- `0x140001cee`
- `0x140001cfa`
- `0x140001d1e`
- `0x140001d2a`
- `0x140001d66`
- `0x140001d96`
- `0x140001da2`
- `0x140001dde`
- `0x140001e0e`
- `0x1400059e8`
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
  char **initial_narrow_environment; // rdi
  char **v11; // rbx
  int *v12; // rax

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
    initial_narrow_environment = get_initial_narrow_environment();
    v11 = *_p___argv();
    v12 = _p___argc();
    main(*v12, (const char **)v11, (const char **)initial_narrow_environment);
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
0x1400012a0  mov     [rsp+arg_0], rbx
0x1400012a5  mov     [rsp+arg_8], rsi
0x1400012aa  push    rdi
0x1400012ab  sub     rsp, 30h
0x1400012af  mov     ecx, 1
0x1400012b4  call    __scrt_initialize_crt
0x1400012b9  test    al, al
0x1400012bb  jz      loc_1400013F6
0x1400012c1  xor     sil, sil
0x1400012c4  mov     [rsp+38h+var_18], sil
0x1400012c9  call    __scrt_acquire_startup_lock
0x1400012ce  mov     bl, al
0x1400012d0  mov     ecx, cs:__scrt_current_native_startup_state
0x1400012d6  cmp     ecx, 1
0x1400012d9  jz      loc_140001401
0x1400012df  test    ecx, ecx
0x1400012e1  jnz     short loc_14000132D
0x1400012e3  mov     cs:__scrt_current_native_startup_state, 1
0x1400012ed  lea     rdx, __xi_z; Last
0x1400012f4  lea     rcx, __xi_a; First
0x1400012fb  call    _initterm_e_0
0x140001300  test    eax, eax
0x140001302  jz      short loc_14000130E
0x140001304  mov     eax, 0FFh
0x140001309  jmp     loc_1400013E6
0x14000130e  lea     rdx, __xc_z; Last
0x140001315  lea     rcx, __xc_a; First
0x14000131c  call    _initterm_0
0x140001321  mov     cs:__scrt_current_native_startup_state, 2
0x14000132b  jmp     short loc_140001335
0x14000132d  mov     sil, 1
0x140001330  mov     [rsp+38h+var_18], sil
0x140001335  mov     cl, bl
0x140001337  call    __scrt_release_startup_lock
0x14000133c  call    __scrt_get_dyn_tls_init_callback
0x140001341  mov     rbx, rax
0x140001344  cmp     qword ptr [rax], 0
0x140001348  jz      short loc_140001367
0x14000134a  mov     rcx, rax
0x14000134d  call    __scrt_is_nonwritable_in_current_image
0x140001352  test    al, al
0x140001354  jz      short loc_140001367
0x140001356  xor     r8d, r8d
0x140001359  lea     edx, [r8+2]
0x14000135d  xor     ecx, ecx
0x14000135f  mov     rax, [rbx]
0x140001362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001367  call    __scrt_get_dyn_tls_dtor_callback
0x14000136c  mov     rbx, rax
0x14000136f  cmp     qword ptr [rax], 0
0x140001373  jz      short loc_140001389
0x140001375  mov     rcx, rax
0x140001378  call    __scrt_is_nonwritable_in_current_image
0x14000137d  test    al, al
0x14000137f  jz      short loc_140001389
0x140001381  mov     rcx, [rbx]; Callback
0x140001384  call    _register_thread_local_exe_atexit_callback_0
0x140001389  call    _get_initial_narrow_environment
0x14000138e  mov     rdi, rax
0x140001391  call    __p___argv
0x140001396  mov     rbx, [rax]
0x140001399  call    __p___argc
0x14000139e  mov     r8, rdi; envp
0x1400013a1  mov     rdx, rbx; argv
0x1400013a4  mov     ecx, [rax]; argc
0x1400013a6  call    main
0x1400013ab  mov     ebx, eax
0x1400013ad  call    __scrt_is_managed_app
0x1400013b2  test    al, al
0x1400013b4  jz      short loc_14000140B
0x1400013b6  test    sil, sil
0x1400013b9  jnz     short loc_1400013C0
0x1400013bb  call    _o__cexit_0
0x1400013c0  xor     edx, edx
0x1400013c2  mov     cl, 1
0x1400013c4  call    __scrt_uninitialize_crt
0x1400013c9  mov     eax, ebx
0x1400013cb  jmp     short loc_1400013E6
0x1400013cd  mov     ebx, eax
0x1400013cf  call    __scrt_is_managed_app
0x1400013d4  test    al, al
0x1400013d6  jz      short loc_140001413
0x1400013d8  cmp     [rsp+38h+var_18], 0
0x1400013dd  jnz     short loc_1400013E4
0x1400013df  call    _c_exit_0
0x1400013e4  mov     eax, ebx
0x1400013e6  mov     rbx, [rsp+38h+arg_0]
0x1400013eb  mov     rsi, [rsp+38h+arg_8]
0x1400013f0  add     rsp, 30h
0x1400013f4  pop     rdi
0x1400013f5  retn
0x1400013f6  mov     ecx, 7
0x1400013fb  call    __scrt_fastfail
0x140001401  mov     ecx, 7
0x140001406  call    __scrt_fastfail
0x14000140b  mov     ecx, ebx; Code
0x14000140d  call    _o_exit_0
0x140001413  mov     ecx, ebx
0x140001415  call    _o__exit_0
0x14000141a  nop
0x140005ddc  push    rbp
0x140005dde  sub     rsp, 20h
0x140005de2  mov     rbp, rdx
0x140005de5  mov     rdx, rcx; ExceptionPtr
0x140005de8  mov     rcx, [rcx]
0x140005deb  mov     ecx, [rcx]; ExceptionNum
0x140005ded  call    _seh_filter_exe
0x140005df2  nop
0x140005df3  add     rsp, 20h
0x140005df7  pop     rbp
0x140005df8  retn
```
