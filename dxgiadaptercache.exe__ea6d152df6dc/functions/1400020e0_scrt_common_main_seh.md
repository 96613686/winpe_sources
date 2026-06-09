# __scrt_common_main_seh

- ea: `0x1400020e0`
- end: `0x14000225b`
- name: `__scrt_common_main_seh`
- size: `379`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x140002270`

## callees

- `0x1400020e0`
- `0x140002308`
- `0x140002348`
- `0x14000241c`
- `0x1400024bc`
- `0x1400024e8`
- `0x1400026ec`
- `0x1400026fc`
- `0x14000270c`
- `0x140002724`
- `0x140002ba6`
- `0x140002bb2`
- `0x140002bbe`
- `0x140002bca`
- `0x140002bee`
- `0x140002bfa`
- `0x140002c42`
- `0x140002c72`
- `0x140002c7e`
- `0x140002cc8`
- `0x140002cf8`
- `0x1400110b8`
- `0x140012010`

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
0x1400020e0  mov     [rsp+arg_0], rbx
0x1400020e5  mov     [rsp+arg_8], rsi
0x1400020ea  push    rdi
0x1400020eb  sub     rsp, 30h
0x1400020ef  mov     ecx, 1
0x1400020f4  call    __scrt_initialize_crt
0x1400020f9  test    al, al
0x1400020fb  jz      loc_140002236
0x140002101  xor     sil, sil
0x140002104  mov     [rsp+38h+var_18], sil
0x140002109  call    __scrt_acquire_startup_lock
0x14000210e  mov     bl, al
0x140002110  mov     ecx, cs:__scrt_current_native_startup_state
0x140002116  cmp     ecx, 1
0x140002119  jz      loc_140002241
0x14000211f  test    ecx, ecx
0x140002121  jnz     short loc_14000216D
0x140002123  mov     cs:__scrt_current_native_startup_state, 1
0x14000212d  lea     rdx, __xi_z; Last
0x140002134  lea     rcx, __xi_a; First
0x14000213b  call    _initterm_e_0
0x140002140  test    eax, eax
0x140002142  jz      short loc_14000214E
0x140002144  mov     eax, 0FFh
0x140002149  jmp     loc_140002226
0x14000214e  lea     rdx, __xc_z; Last
0x140002155  lea     rcx, __xc_a; First
0x14000215c  call    _initterm_0
0x140002161  mov     cs:__scrt_current_native_startup_state, 2
0x14000216b  jmp     short loc_140002175
0x14000216d  mov     sil, 1
0x140002170  mov     [rsp+38h+var_18], sil
0x140002175  mov     cl, bl
0x140002177  call    __scrt_release_startup_lock
0x14000217c  call    __scrt_get_dyn_tls_init_callback
0x140002181  mov     rbx, rax
0x140002184  cmp     qword ptr [rax], 0
0x140002188  jz      short loc_1400021A7
0x14000218a  mov     rcx, rax
0x14000218d  call    __scrt_is_nonwritable_in_current_image
0x140002192  test    al, al
0x140002194  jz      short loc_1400021A7
0x140002196  xor     r8d, r8d
0x140002199  lea     edx, [r8+2]
0x14000219d  xor     ecx, ecx
0x14000219f  mov     rax, [rbx]
0x1400021a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400021a7  call    __scrt_get_dyn_tls_dtor_callback
0x1400021ac  mov     rbx, rax
0x1400021af  cmp     qword ptr [rax], 0
0x1400021b3  jz      short loc_1400021C9
0x1400021b5  mov     rcx, rax
0x1400021b8  call    __scrt_is_nonwritable_in_current_image
0x1400021bd  test    al, al
0x1400021bf  jz      short loc_1400021C9
0x1400021c1  mov     rcx, [rbx]; Callback
0x1400021c4  call    _register_thread_local_exe_atexit_callback_0
0x1400021c9  call    _get_initial_wide_environment
0x1400021ce  mov     rdi, rax
0x1400021d1  call    __p___wargv
0x1400021d6  mov     rbx, [rax]
0x1400021d9  call    __p___argc
0x1400021de  mov     r8, rdi
0x1400021e1  mov     rdx, rbx
0x1400021e4  mov     ecx, [rax]
0x1400021e6  call    wmain
0x1400021eb  mov     ebx, eax
0x1400021ed  call    __scrt_is_managed_app
0x1400021f2  test    al, al
0x1400021f4  jz      short loc_14000224B
0x1400021f6  test    sil, sil
0x1400021f9  jnz     short loc_140002200
0x1400021fb  call    _o__cexit_0
0x140002200  xor     edx, edx
0x140002202  mov     cl, 1
0x140002204  call    __scrt_uninitialize_crt
0x140002209  mov     eax, ebx
0x14000220b  jmp     short loc_140002226
0x14000220d  mov     ebx, eax
0x14000220f  call    __scrt_is_managed_app
0x140002214  test    al, al
0x140002216  jz      short loc_140002253
0x140002218  cmp     [rsp+38h+var_18], 0
0x14000221d  jnz     short loc_140002224
0x14000221f  call    _c_exit_0
0x140002224  mov     eax, ebx
0x140002226  mov     rbx, [rsp+38h+arg_0]
0x14000222b  mov     rsi, [rsp+38h+arg_8]
0x140002230  add     rsp, 30h
0x140002234  pop     rdi
0x140002235  retn
0x140002236  mov     ecx, 7
0x14000223b  call    __scrt_fastfail
0x140002241  mov     ecx, 7
0x140002246  call    __scrt_fastfail
0x14000224b  mov     ecx, ebx; Code
0x14000224d  call    _o_exit_0
0x140002253  mov     ecx, ebx
0x140002255  call    _o__exit_0
0x14000225a  nop
0x14001149c  push    rbp
0x14001149e  sub     rsp, 20h
0x1400114a2  mov     rbp, rdx
0x1400114a5  mov     rdx, rcx; ExceptionPtr
0x1400114a8  mov     rcx, [rcx]
0x1400114ab  mov     ecx, [rcx]; ExceptionNum
0x1400114ad  call    _seh_filter_exe
0x1400114b2  nop
0x1400114b3  add     rsp, 20h
0x1400114b7  pop     rbp
0x1400114b8  retn
```
