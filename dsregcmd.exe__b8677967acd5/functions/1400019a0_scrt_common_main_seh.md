# __scrt_common_main_seh

- ea: `0x1400019a0`
- end: `0x140001b1b`
- name: `__scrt_common_main_seh`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x140001b30`

## callees

- `0x1400019a0`
- `0x140001e5c`
- `0x140001e9c`
- `0x140001f70`
- `0x140002010`
- `0x14000203c`
- `0x1400021d8`
- `0x1400021e8`
- `0x1400021f8`
- `0x140002210`
- `0x140002646`
- `0x140002652`
- `0x14000265e`
- `0x14000266a`
- `0x14000268e`
- `0x14000269a`
- `0x1400026ee`
- `0x14000271e`
- `0x14000272a`
- `0x140002778`
- `0x1400027b4`
- `0x140002a94`
- `0x140030010`

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
0x1400019a0  mov     [rsp+arg_0], rbx
0x1400019a5  mov     [rsp+arg_8], rsi
0x1400019aa  push    rdi
0x1400019ab  sub     rsp, 30h
0x1400019af  mov     ecx, 1
0x1400019b4  call    __scrt_initialize_crt
0x1400019b9  test    al, al
0x1400019bb  jz      loc_140001AF6
0x1400019c1  xor     sil, sil
0x1400019c4  mov     [rsp+38h+var_18], sil
0x1400019c9  call    __scrt_acquire_startup_lock
0x1400019ce  mov     bl, al
0x1400019d0  mov     ecx, cs:__scrt_current_native_startup_state
0x1400019d6  cmp     ecx, 1
0x1400019d9  jz      loc_140001B01
0x1400019df  test    ecx, ecx
0x1400019e1  jnz     short loc_140001A2D
0x1400019e3  mov     cs:__scrt_current_native_startup_state, 1
0x1400019ed  lea     rdx, __xi_z; Last
0x1400019f4  lea     rcx, __xi_a; First
0x1400019fb  call    _initterm_e_0
0x140001a00  test    eax, eax
0x140001a02  jz      short loc_140001A0E
0x140001a04  mov     eax, 0FFh
0x140001a09  jmp     loc_140001AE6
0x140001a0e  lea     rdx, __xc_z; Last
0x140001a15  lea     rcx, __xc_a; First
0x140001a1c  call    _initterm_0
0x140001a21  mov     cs:__scrt_current_native_startup_state, 2
0x140001a2b  jmp     short loc_140001A35
0x140001a2d  mov     sil, 1
0x140001a30  mov     [rsp+38h+var_18], sil
0x140001a35  mov     cl, bl
0x140001a37  call    __scrt_release_startup_lock
0x140001a3c  call    __scrt_get_dyn_tls_init_callback
0x140001a41  mov     rbx, rax
0x140001a44  cmp     qword ptr [rax], 0
0x140001a48  jz      short loc_140001A67
0x140001a4a  mov     rcx, rax
0x140001a4d  call    __scrt_is_nonwritable_in_current_image
0x140001a52  test    al, al
0x140001a54  jz      short loc_140001A67
0x140001a56  xor     r8d, r8d
0x140001a59  lea     edx, [r8+2]
0x140001a5d  xor     ecx, ecx
0x140001a5f  mov     rax, [rbx]
0x140001a62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001a67  call    __scrt_get_dyn_tls_dtor_callback
0x140001a6c  mov     rbx, rax
0x140001a6f  cmp     qword ptr [rax], 0
0x140001a73  jz      short loc_140001A89
0x140001a75  mov     rcx, rax
0x140001a78  call    __scrt_is_nonwritable_in_current_image
0x140001a7d  test    al, al
0x140001a7f  jz      short loc_140001A89
0x140001a81  mov     rcx, [rbx]; Callback
0x140001a84  call    _register_thread_local_exe_atexit_callback_0
0x140001a89  call    _get_initial_wide_environment
0x140001a8e  mov     rdi, rax
0x140001a91  call    __p___wargv
0x140001a96  mov     rbx, [rax]
0x140001a99  call    __p___argc
0x140001a9e  mov     r8, rdi
0x140001aa1  mov     rdx, rbx
0x140001aa4  mov     ecx, [rax]
0x140001aa6  call    wmain
0x140001aab  mov     ebx, eax
0x140001aad  call    __scrt_is_managed_app
0x140001ab2  test    al, al
0x140001ab4  jz      short loc_140001B0B
0x140001ab6  test    sil, sil
0x140001ab9  jnz     short loc_140001AC0
0x140001abb  call    _o__cexit_0
0x140001ac0  xor     edx, edx
0x140001ac2  mov     cl, 1
0x140001ac4  call    __scrt_uninitialize_crt
0x140001ac9  mov     eax, ebx
0x140001acb  jmp     short loc_140001AE6
0x140001acd  mov     ebx, eax
0x140001acf  call    __scrt_is_managed_app
0x140001ad4  test    al, al
0x140001ad6  jz      short loc_140001B13
0x140001ad8  cmp     [rsp+38h+var_18], 0
0x140001add  jnz     short loc_140001AE4
0x140001adf  call    _c_exit_0
0x140001ae4  mov     eax, ebx
0x140001ae6  mov     rbx, [rsp+38h+arg_0]
0x140001aeb  mov     rsi, [rsp+38h+arg_8]
0x140001af0  add     rsp, 30h
0x140001af4  pop     rdi
0x140001af5  retn
0x140001af6  mov     ecx, 7
0x140001afb  call    __scrt_fastfail
0x140001b01  mov     ecx, 7
0x140001b06  call    __scrt_fastfail
0x140001b0b  mov     ecx, ebx; Code
0x140001b0d  call    _o_exit_0
0x140001b13  mov     ecx, ebx
0x140001b15  call    _o__exit_0
0x140001b1a  nop
0x14002c48c  push    rbp
0x14002c48e  sub     rsp, 20h
0x14002c492  mov     rbp, rdx
0x14002c495  mov     rdx, rcx; ExceptionPtr
0x14002c498  mov     rcx, [rcx]
0x14002c49b  mov     ecx, [rcx]; ExceptionNum
0x14002c49d  call    _seh_filter_exe
0x14002c4a2  nop
0x14002c4a3  add     rsp, 20h
0x14002c4a7  pop     rbp
0x14002c4a8  retn
```
