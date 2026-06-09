# __scrt_common_main_seh

- ea: `0x1400027e0`
- end: `0x14000295b`
- name: `__scrt_common_main_seh`
- size: `379`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x140002970`

## callees

- `0x1400027e0`
- `0x1400029fc`
- `0x140002a3c`
- `0x140002b10`
- `0x140002bb0`
- `0x140002bdc`
- `0x140002db4`
- `0x140002dc4`
- `0x140002dd4`
- `0x140002dec`
- `0x1400031f6`
- `0x140003202`
- `0x14000320e`
- `0x14000321a`
- `0x14000323e`
- `0x14000324a`
- `0x140003286`
- `0x1400032b6`
- `0x1400032c2`
- `0x140003318`
- `0x140003348`
- `0x14000ad00`
- `0x140018010`

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
0x1400027e0  mov     [rsp+arg_0], rbx
0x1400027e5  mov     [rsp+arg_8], rsi
0x1400027ea  push    rdi
0x1400027eb  sub     rsp, 30h
0x1400027ef  mov     ecx, 1
0x1400027f4  call    __scrt_initialize_crt
0x1400027f9  test    al, al
0x1400027fb  jz      loc_140002936
0x140002801  xor     sil, sil
0x140002804  mov     [rsp+38h+var_18], sil
0x140002809  call    __scrt_acquire_startup_lock
0x14000280e  mov     bl, al
0x140002810  mov     ecx, cs:__scrt_current_native_startup_state
0x140002816  cmp     ecx, 1
0x140002819  jz      loc_140002941
0x14000281f  test    ecx, ecx
0x140002821  jnz     short loc_14000286D
0x140002823  mov     cs:__scrt_current_native_startup_state, 1
0x14000282d  lea     rdx, __xi_z; Last
0x140002834  lea     rcx, __xi_a; First
0x14000283b  call    _initterm_e_0
0x140002840  test    eax, eax
0x140002842  jz      short loc_14000284E
0x140002844  mov     eax, 0FFh
0x140002849  jmp     loc_140002926
0x14000284e  lea     rdx, __xc_z; Last
0x140002855  lea     rcx, __xc_a; First
0x14000285c  call    _initterm_0
0x140002861  mov     cs:__scrt_current_native_startup_state, 2
0x14000286b  jmp     short loc_140002875
0x14000286d  mov     sil, 1
0x140002870  mov     [rsp+38h+var_18], sil
0x140002875  mov     cl, bl
0x140002877  call    __scrt_release_startup_lock
0x14000287c  call    __scrt_get_dyn_tls_init_callback
0x140002881  mov     rbx, rax
0x140002884  cmp     qword ptr [rax], 0
0x140002888  jz      short loc_1400028A7
0x14000288a  mov     rcx, rax
0x14000288d  call    __scrt_is_nonwritable_in_current_image
0x140002892  test    al, al
0x140002894  jz      short loc_1400028A7
0x140002896  xor     r8d, r8d
0x140002899  lea     edx, [r8+2]
0x14000289d  xor     ecx, ecx
0x14000289f  mov     rax, [rbx]
0x1400028a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400028a7  call    __scrt_get_dyn_tls_dtor_callback
0x1400028ac  mov     rbx, rax
0x1400028af  cmp     qword ptr [rax], 0
0x1400028b3  jz      short loc_1400028C9
0x1400028b5  mov     rcx, rax
0x1400028b8  call    __scrt_is_nonwritable_in_current_image
0x1400028bd  test    al, al
0x1400028bf  jz      short loc_1400028C9
0x1400028c1  mov     rcx, [rbx]; Callback
0x1400028c4  call    _register_thread_local_exe_atexit_callback_0
0x1400028c9  call    _get_initial_narrow_environment
0x1400028ce  mov     rdi, rax
0x1400028d1  call    __p___argv
0x1400028d6  mov     rbx, [rax]
0x1400028d9  call    __p___argc
0x1400028de  mov     r8, rdi; envp
0x1400028e1  mov     rdx, rbx; argv
0x1400028e4  mov     ecx, [rax]; argc
0x1400028e6  call    main
0x1400028eb  mov     ebx, eax
0x1400028ed  call    __scrt_is_managed_app
0x1400028f2  test    al, al
0x1400028f4  jz      short loc_14000294B
0x1400028f6  test    sil, sil
0x1400028f9  jnz     short loc_140002900
0x1400028fb  call    _o__cexit_0
0x140002900  xor     edx, edx
0x140002902  mov     cl, 1
0x140002904  call    __scrt_uninitialize_crt
0x140002909  mov     eax, ebx
0x14000290b  jmp     short loc_140002926
0x14000290d  mov     ebx, eax
0x14000290f  call    __scrt_is_managed_app
0x140002914  test    al, al
0x140002916  jz      short loc_140002953
0x140002918  cmp     [rsp+38h+var_18], 0
0x14000291d  jnz     short loc_140002924
0x14000291f  call    _c_exit_0
0x140002924  mov     eax, ebx
0x140002926  mov     rbx, [rsp+38h+arg_0]
0x14000292b  mov     rsi, [rsp+38h+arg_8]
0x140002930  add     rsp, 30h
0x140002934  pop     rdi
0x140002935  retn
0x140002936  mov     ecx, 7
0x14000293b  call    __scrt_fastfail
0x140002941  mov     ecx, 7
0x140002946  call    __scrt_fastfail
0x14000294b  mov     ecx, ebx; Code
0x14000294d  call    _o_exit_0
0x140002953  mov     ecx, ebx
0x140002955  call    _o__exit_0
0x14000295a  nop
0x14001776c  push    rbp
0x14001776e  sub     rsp, 20h
0x140017772  mov     rbp, rdx
0x140017775  mov     rdx, rcx; ExceptionPtr
0x140017778  mov     rcx, [rcx]
0x14001777b  mov     ecx, [rcx]; ExceptionNum
0x14001777d  call    _seh_filter_exe
0x140017782  nop
0x140017783  add     rsp, 20h
0x140017787  pop     rbp
0x140017788  retn
```
