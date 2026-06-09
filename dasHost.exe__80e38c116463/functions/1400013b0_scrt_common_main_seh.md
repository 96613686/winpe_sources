# __scrt_common_main_seh

- ea: `0x1400013b0`
- end: `0x14000152b`
- name: `__scrt_common_main_seh`
- size: `379`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x140001540`

## callees

- `0x1400013b0`
- `0x140001664`
- `0x1400016a4`
- `0x140001778`
- `0x140001818`
- `0x140001844`
- `0x140001a68`
- `0x140001a78`
- `0x140001a88`
- `0x140001aa0`
- `0x140001f26`
- `0x140001f32`
- `0x140001f3e`
- `0x140001f4a`
- `0x140001f7a`
- `0x140001f86`
- `0x140001fce`
- `0x140001ffe`
- `0x14000200a`
- `0x140002058`
- `0x140002088`
- `0x140010928`
- `0x14001c010`

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
  wchar_t **initial_wide_environment; // rdi
  wchar_t **v12; // rbx
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
  initial_wide_environment = get_initial_wide_environment();
  v12 = *_p___wargv();
  v13 = _p___argc();
  v14 = wmain((unsigned int)*v13, v12, initial_wide_environment);
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
0x1400013b0  mov     [rsp+arg_0], rbx
0x1400013b5  mov     [rsp+arg_8], rsi
0x1400013ba  push    rdi
0x1400013bb  sub     rsp, 30h
0x1400013bf  mov     ecx, 1
0x1400013c4  call    __scrt_initialize_crt
0x1400013c9  test    al, al
0x1400013cb  jz      loc_140001506
0x1400013d1  xor     sil, sil
0x1400013d4  mov     [rsp+38h+var_18], sil
0x1400013d9  call    __scrt_acquire_startup_lock
0x1400013de  mov     bl, al
0x1400013e0  mov     ecx, cs:__scrt_current_native_startup_state
0x1400013e6  cmp     ecx, 1
0x1400013e9  jz      loc_140001511
0x1400013ef  test    ecx, ecx
0x1400013f1  jnz     short loc_14000143D
0x1400013f3  mov     cs:__scrt_current_native_startup_state, 1
0x1400013fd  lea     rdx, __xi_z; Last
0x140001404  lea     rcx, __xi_a; First
0x14000140b  call    _initterm_e_0
0x140001410  test    eax, eax
0x140001412  jz      short loc_14000141E
0x140001414  mov     eax, 0FFh
0x140001419  jmp     loc_1400014F6
0x14000141e  lea     rdx, __xc_z; Last
0x140001425  lea     rcx, __xc_a; First
0x14000142c  call    _initterm_0
0x140001431  mov     cs:__scrt_current_native_startup_state, 2
0x14000143b  jmp     short loc_140001445
0x14000143d  mov     sil, 1
0x140001440  mov     [rsp+38h+var_18], sil
0x140001445  mov     cl, bl
0x140001447  call    __scrt_release_startup_lock
0x14000144c  call    __scrt_get_dyn_tls_init_callback
0x140001451  mov     rbx, rax
0x140001454  cmp     qword ptr [rax], 0
0x140001458  jz      short loc_140001477
0x14000145a  mov     rcx, rax
0x14000145d  call    __scrt_is_nonwritable_in_current_image
0x140001462  test    al, al
0x140001464  jz      short loc_140001477
0x140001466  xor     r8d, r8d
0x140001469  lea     edx, [r8+2]
0x14000146d  xor     ecx, ecx
0x14000146f  mov     rax, [rbx]
0x140001472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001477  call    __scrt_get_dyn_tls_dtor_callback
0x14000147c  mov     rbx, rax
0x14000147f  cmp     qword ptr [rax], 0
0x140001483  jz      short loc_140001499
0x140001485  mov     rcx, rax
0x140001488  call    __scrt_is_nonwritable_in_current_image
0x14000148d  test    al, al
0x14000148f  jz      short loc_140001499
0x140001491  mov     rcx, [rbx]; Callback
0x140001494  call    _register_thread_local_exe_atexit_callback_0
0x140001499  call    _get_initial_wide_environment
0x14000149e  mov     rdi, rax
0x1400014a1  call    __p___wargv
0x1400014a6  mov     rbx, [rax]
0x1400014a9  call    __p___argc
0x1400014ae  mov     r8, rdi
0x1400014b1  mov     rdx, rbx
0x1400014b4  mov     ecx, [rax]
0x1400014b6  call    wmain
0x1400014bb  mov     ebx, eax
0x1400014bd  call    __scrt_is_managed_app
0x1400014c2  test    al, al
0x1400014c4  jz      short loc_14000151B
0x1400014c6  test    sil, sil
0x1400014c9  jnz     short loc_1400014D0
0x1400014cb  call    _o__cexit_0
0x1400014d0  xor     edx, edx
0x1400014d2  mov     cl, 1
0x1400014d4  call    __scrt_uninitialize_crt
0x1400014d9  mov     eax, ebx
0x1400014db  jmp     short loc_1400014F6
0x1400014dd  mov     ebx, eax
0x1400014df  call    __scrt_is_managed_app
0x1400014e4  test    al, al
0x1400014e6  jz      short loc_140001523
0x1400014e8  cmp     [rsp+38h+var_18], 0
0x1400014ed  jnz     short loc_1400014F4
0x1400014ef  call    _c_exit_0
0x1400014f4  mov     eax, ebx
0x1400014f6  mov     rbx, [rsp+38h+arg_0]
0x1400014fb  mov     rsi, [rsp+38h+arg_8]
0x140001500  add     rsp, 30h
0x140001504  pop     rdi
0x140001505  retn
0x140001506  mov     ecx, 7
0x14000150b  call    __scrt_fastfail
0x140001511  mov     ecx, 7
0x140001516  call    __scrt_fastfail
0x14000151b  mov     ecx, ebx; Code
0x14000151d  call    _o_exit_0
0x140001523  mov     ecx, ebx
0x140001525  call    _o__exit_0
0x14000152a  nop
0x14001a8bc  push    rbp
0x14001a8be  sub     rsp, 20h
0x14001a8c2  mov     rbp, rdx
0x14001a8c5  mov     rdx, rcx; ExceptionPtr
0x14001a8c8  mov     rcx, [rcx]
0x14001a8cb  mov     ecx, [rcx]; ExceptionNum
0x14001a8cd  call    _seh_filter_exe
0x14001a8d2  nop
0x14001a8d3  add     rsp, 20h
0x14001a8d7  pop     rbp
0x14001a8d8  retn
```
