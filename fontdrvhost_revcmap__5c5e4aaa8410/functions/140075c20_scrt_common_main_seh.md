# __scrt_common_main_seh

- ea: `0x140075c20`
- end: `0x140075d9b`
- name: `__scrt_common_main_seh`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x140075db0`

## callees

- `0x140067a40`
- `0x140075c20`
- `0x140075e04`
- `0x140075e44`
- `0x140075f18`
- `0x140075fb8`
- `0x140075fe4`
- `0x1400761b8`
- `0x1400761c8`
- `0x1400761d8`
- `0x1400761f0`
- `0x140076636`
- `0x140076642`
- `0x14007664e`
- `0x14007665a`
- `0x140076696`
- `0x1400766a2`
- `0x140076702`
- `0x140076732`
- `0x14007673e`
- `0x140076788`
- `0x1400767b8`
- `0x140098010`

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
  char **initial_narrow_environment; // rdi
  char **v12; // rbx
  int *v13; // rax
  unsigned int v14; // ebx
  __int64 v15; // rcx
  __int64 v16; // rcx

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
  initial_narrow_environment = get_initial_narrow_environment();
  v12 = *_p___argv();
  v13 = _p___argc();
  v14 = main(*v13, (const char **)v12, (const char **)initial_narrow_environment);
  if ( !(unsigned __int8)_scrt_is_managed_app(v15) )
    o_exit_0(v14);
  if ( !v1 )
    o__cexit_0(v16);
  LOBYTE(v16) = 1;
  _scrt_uninitialize_crt(v16, 0);
  return v14;
}

```

## disassembly

```asm
0x140075c20  mov     [rsp+arg_0], rbx
0x140075c25  mov     [rsp+arg_8], rsi
0x140075c2a  push    rdi
0x140075c2b  sub     rsp, 30h
0x140075c2f  mov     ecx, 1
0x140075c34  call    __scrt_initialize_crt
0x140075c39  test    al, al
0x140075c3b  jz      loc_140075D76
0x140075c41  xor     sil, sil
0x140075c44  mov     [rsp+38h+var_18], sil
0x140075c49  call    __scrt_acquire_startup_lock
0x140075c4e  mov     bl, al
0x140075c50  mov     ecx, cs:__scrt_current_native_startup_state
0x140075c56  cmp     ecx, 1
0x140075c59  jz      loc_140075D81
0x140075c5f  test    ecx, ecx
0x140075c61  jnz     short loc_140075CAD
0x140075c63  mov     cs:__scrt_current_native_startup_state, 1
0x140075c6d  lea     rdx, __xi_z; Last
0x140075c74  lea     rcx, __xi_a; First
0x140075c7b  call    _initterm_e_0
0x140075c80  test    eax, eax
0x140075c82  jz      short loc_140075C8E
0x140075c84  mov     eax, 0FFh
0x140075c89  jmp     loc_140075D66
0x140075c8e  lea     rdx, __xc_z; Last
0x140075c95  lea     rcx, __xc_a; First
0x140075c9c  call    _initterm_0
0x140075ca1  mov     cs:__scrt_current_native_startup_state, 2
0x140075cab  jmp     short loc_140075CB5
0x140075cad  mov     sil, 1
0x140075cb0  mov     [rsp+38h+var_18], sil
0x140075cb5  mov     cl, bl
0x140075cb7  call    __scrt_release_startup_lock
0x140075cbc  call    __scrt_get_dyn_tls_init_callback
0x140075cc1  mov     rbx, rax
0x140075cc4  cmp     qword ptr [rax], 0
0x140075cc8  jz      short loc_140075CE7
0x140075cca  mov     rcx, rax
0x140075ccd  call    __scrt_is_nonwritable_in_current_image
0x140075cd2  test    al, al
0x140075cd4  jz      short loc_140075CE7
0x140075cd6  xor     r8d, r8d
0x140075cd9  lea     edx, [r8+2]
0x140075cdd  xor     ecx, ecx
0x140075cdf  mov     rax, [rbx]
0x140075ce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140075ce7  call    __scrt_get_dyn_tls_dtor_callback
0x140075cec  mov     rbx, rax
0x140075cef  cmp     qword ptr [rax], 0
0x140075cf3  jz      short loc_140075D09
0x140075cf5  mov     rcx, rax
0x140075cf8  call    __scrt_is_nonwritable_in_current_image
0x140075cfd  test    al, al
0x140075cff  jz      short loc_140075D09
0x140075d01  mov     rcx, [rbx]; Callback
0x140075d04  call    _register_thread_local_exe_atexit_callback_0
0x140075d09  call    _get_initial_narrow_environment
0x140075d0e  mov     rdi, rax
0x140075d11  call    __p___argv
0x140075d16  mov     rbx, [rax]
0x140075d19  call    __p___argc
0x140075d1e  mov     r8, rdi; envp
0x140075d21  mov     rdx, rbx; argv
0x140075d24  mov     ecx, [rax]; argc
0x140075d26  call    main
0x140075d2b  mov     ebx, eax
0x140075d2d  call    __scrt_is_managed_app
0x140075d32  test    al, al
0x140075d34  jz      short loc_140075D8B
0x140075d36  test    sil, sil
0x140075d39  jnz     short loc_140075D40
0x140075d3b  call    _o__cexit_0
0x140075d40  xor     edx, edx
0x140075d42  mov     cl, 1
0x140075d44  call    __scrt_uninitialize_crt
0x140075d49  mov     eax, ebx
0x140075d4b  jmp     short loc_140075D66
0x140075d4d  mov     ebx, eax
0x140075d4f  call    __scrt_is_managed_app
0x140075d54  test    al, al
0x140075d56  jz      short loc_140075D93
0x140075d58  cmp     [rsp+38h+var_18], 0
0x140075d5d  jnz     short loc_140075D64
0x140075d5f  call    _c_exit_0
0x140075d64  mov     eax, ebx
0x140075d66  mov     rbx, [rsp+38h+arg_0]
0x140075d6b  mov     rsi, [rsp+38h+arg_8]
0x140075d70  add     rsp, 30h
0x140075d74  pop     rdi
0x140075d75  retn
0x140075d76  mov     ecx, 7
0x140075d7b  call    __scrt_fastfail
0x140075d81  mov     ecx, 7
0x140075d86  call    __scrt_fastfail
0x140075d8b  mov     ecx, ebx; Code
0x140075d8d  call    _o_exit_0
0x140075d93  mov     ecx, ebx
0x140075d95  call    _o__exit_0
0x140075d9a  nop
0x1400976e0  push    rbp
0x1400976e2  sub     rsp, 20h
0x1400976e6  mov     rbp, rdx
0x1400976e9  mov     rdx, rcx; ExceptionPtr
0x1400976ec  mov     rcx, [rcx]
0x1400976ef  mov     ecx, [rcx]; ExceptionNum
0x1400976f1  call    _seh_filter_exe
0x1400976f6  nop
0x1400976f7  add     rsp, 20h
0x1400976fb  pop     rbp
0x1400976fc  retn
```
