# __scrt_common_main_seh

- ea: `0x140002da0`
- end: `0x140002f1b`
- name: `__scrt_common_main_seh`
- size: `379`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x140002f30`

## callees

- `0x140002da0`
- `0x140002fc8`
- `0x140003008`
- `0x1400030dc`
- `0x14000317c`
- `0x1400031a8`
- `0x14000370c`
- `0x14000371c`
- `0x14000372c`
- `0x140003744`
- `0x140003936`
- `0x140003942`
- `0x14000394e`
- `0x14000395a`
- `0x14000398a`
- `0x140003996`
- `0x140003a0e`
- `0x140003a3e`
- `0x140003a4a`
- `0x140003a98`
- `0x140003ad4`
- `0x140034cf8`
- `0x14003e010`

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
  BOOL v11; // ebx
  __int64 v12; // rcx
  __int64 v13; // rcx

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
  _p___wargv();
  _p___argc();
  v11 = wmain();
  if ( !(unsigned __int8)_scrt_is_managed_app(v12) )
    o_exit_0(v11);
  if ( !v1 )
    o__cexit_0(v13);
  LOBYTE(v13) = 1;
  _scrt_uninitialize_crt(v13, 0);
  return v11;
}

```

## disassembly

```asm
0x140002da0  mov     [rsp+arg_0], rbx
0x140002da5  mov     [rsp+arg_8], rsi
0x140002daa  push    rdi
0x140002dab  sub     rsp, 30h
0x140002daf  mov     ecx, 1
0x140002db4  call    __scrt_initialize_crt
0x140002db9  test    al, al
0x140002dbb  jz      loc_140002EF6
0x140002dc1  xor     sil, sil
0x140002dc4  mov     [rsp+38h+var_18], sil
0x140002dc9  call    __scrt_acquire_startup_lock
0x140002dce  mov     bl, al
0x140002dd0  mov     ecx, cs:__scrt_current_native_startup_state
0x140002dd6  cmp     ecx, 1
0x140002dd9  jz      loc_140002F01
0x140002ddf  test    ecx, ecx
0x140002de1  jnz     short loc_140002E2D
0x140002de3  mov     cs:__scrt_current_native_startup_state, 1
0x140002ded  lea     rdx, __xi_z; Last
0x140002df4  lea     rcx, __xi_a; First
0x140002dfb  call    _initterm_e_0
0x140002e00  test    eax, eax
0x140002e02  jz      short loc_140002E0E
0x140002e04  mov     eax, 0FFh
0x140002e09  jmp     loc_140002EE6
0x140002e0e  lea     rdx, __xc_z; Last
0x140002e15  lea     rcx, __xc_a; First
0x140002e1c  call    _initterm_0
0x140002e21  mov     cs:__scrt_current_native_startup_state, 2
0x140002e2b  jmp     short loc_140002E35
0x140002e2d  mov     sil, 1
0x140002e30  mov     [rsp+38h+var_18], sil
0x140002e35  mov     cl, bl
0x140002e37  call    __scrt_release_startup_lock
0x140002e3c  call    __scrt_get_dyn_tls_init_callback
0x140002e41  mov     rbx, rax
0x140002e44  cmp     qword ptr [rax], 0
0x140002e48  jz      short loc_140002E67
0x140002e4a  mov     rcx, rax
0x140002e4d  call    __scrt_is_nonwritable_in_current_image
0x140002e52  test    al, al
0x140002e54  jz      short loc_140002E67
0x140002e56  xor     r8d, r8d
0x140002e59  lea     edx, [r8+2]
0x140002e5d  xor     ecx, ecx
0x140002e5f  mov     rax, [rbx]
0x140002e62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002e67  call    __scrt_get_dyn_tls_dtor_callback
0x140002e6c  mov     rbx, rax
0x140002e6f  cmp     qword ptr [rax], 0
0x140002e73  jz      short loc_140002E89
0x140002e75  mov     rcx, rax
0x140002e78  call    __scrt_is_nonwritable_in_current_image
0x140002e7d  test    al, al
0x140002e7f  jz      short loc_140002E89
0x140002e81  mov     rcx, [rbx]; Callback
0x140002e84  call    _register_thread_local_exe_atexit_callback_0
0x140002e89  call    _get_initial_wide_environment
0x140002e8e  mov     rdi, rax
0x140002e91  call    __p___wargv
0x140002e96  mov     rbx, [rax]
0x140002e99  call    __p___argc
0x140002e9e  mov     r8, rdi
0x140002ea1  mov     rdx, rbx
0x140002ea4  mov     ecx, [rax]
0x140002ea6  call    wmain
0x140002eab  mov     ebx, eax
0x140002ead  call    __scrt_is_managed_app
0x140002eb2  test    al, al
0x140002eb4  jz      short loc_140002F0B
0x140002eb6  test    sil, sil
0x140002eb9  jnz     short loc_140002EC0
0x140002ebb  call    _o__cexit_0
0x140002ec0  xor     edx, edx
0x140002ec2  mov     cl, 1
0x140002ec4  call    __scrt_uninitialize_crt
0x140002ec9  mov     eax, ebx
0x140002ecb  jmp     short loc_140002EE6
0x140002ecd  mov     ebx, eax
0x140002ecf  call    __scrt_is_managed_app
0x140002ed4  test    al, al
0x140002ed6  jz      short loc_140002F13
0x140002ed8  cmp     [rsp+38h+var_18], 0
0x140002edd  jnz     short loc_140002EE4
0x140002edf  call    _c_exit_0
0x140002ee4  mov     eax, ebx
0x140002ee6  mov     rbx, [rsp+38h+arg_0]
0x140002eeb  mov     rsi, [rsp+38h+arg_8]
0x140002ef0  add     rsp, 30h
0x140002ef4  pop     rdi
0x140002ef5  retn
0x140002ef6  mov     ecx, 7
0x140002efb  call    __scrt_fastfail
0x140002f01  mov     ecx, 7
0x140002f06  call    __scrt_fastfail
0x140002f0b  mov     ecx, ebx; Code
0x140002f0d  call    _o_exit_0
0x140002f13  mov     ecx, ebx
0x140002f15  call    _o__exit_0
0x140002f1a  nop
0x14003bd90  push    rbp
0x14003bd92  sub     rsp, 20h
0x14003bd96  mov     rbp, rdx
0x14003bd99  mov     rdx, rcx; ExceptionPtr
0x14003bd9c  mov     rcx, [rcx]
0x14003bd9f  mov     ecx, [rcx]; ExceptionNum
0x14003bda1  call    _seh_filter_exe
0x14003bda6  nop
0x14003bda7  add     rsp, 20h
0x14003bdab  pop     rbp
0x14003bdac  retn
```
