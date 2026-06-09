# __scrt_common_main_seh

- ea: `0x140001a90`
- end: `0x140001c0b`
- name: `__scrt_common_main_seh`
- size: `379`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x140001c20`

## callees

- `0x140001a90`
- `0x140002060`
- `0x1400020a0`
- `0x140002174`
- `0x140002214`
- `0x140002240`
- `0x140002400`
- `0x140002410`
- `0x140002420`
- `0x140002438`
- `0x140002616`
- `0x140002622`
- `0x14000262e`
- `0x14000263a`
- `0x14000266a`
- `0x140002676`
- `0x1400026d6`
- `0x140002706`
- `0x140002712`
- `0x140002742`
- `0x140002772`
- `0x140009ee0`
- `0x14000d010`

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
0x140001a90  mov     [rsp+arg_0], rbx
0x140001a95  mov     [rsp+arg_8], rsi
0x140001a9a  push    rdi
0x140001a9b  sub     rsp, 30h
0x140001a9f  mov     ecx, 1
0x140001aa4  call    __scrt_initialize_crt
0x140001aa9  test    al, al
0x140001aab  jz      loc_140001BE6
0x140001ab1  xor     sil, sil
0x140001ab4  mov     [rsp+38h+var_18], sil
0x140001ab9  call    __scrt_acquire_startup_lock
0x140001abe  mov     bl, al
0x140001ac0  mov     ecx, cs:__scrt_current_native_startup_state
0x140001ac6  cmp     ecx, 1
0x140001ac9  jz      loc_140001BF1
0x140001acf  test    ecx, ecx
0x140001ad1  jnz     short loc_140001B1D
0x140001ad3  mov     cs:__scrt_current_native_startup_state, 1
0x140001add  lea     rdx, __xi_z; Last
0x140001ae4  lea     rcx, __xi_a; First
0x140001aeb  call    _initterm_e_0
0x140001af0  test    eax, eax
0x140001af2  jz      short loc_140001AFE
0x140001af4  mov     eax, 0FFh
0x140001af9  jmp     loc_140001BD6
0x140001afe  lea     rdx, __xc_z; Last
0x140001b05  lea     rcx, __xc_a; First
0x140001b0c  call    _initterm_0
0x140001b11  mov     cs:__scrt_current_native_startup_state, 2
0x140001b1b  jmp     short loc_140001B25
0x140001b1d  mov     sil, 1
0x140001b20  mov     [rsp+38h+var_18], sil
0x140001b25  mov     cl, bl
0x140001b27  call    __scrt_release_startup_lock
0x140001b2c  call    __scrt_get_dyn_tls_init_callback
0x140001b31  mov     rbx, rax
0x140001b34  cmp     qword ptr [rax], 0
0x140001b38  jz      short loc_140001B57
0x140001b3a  mov     rcx, rax
0x140001b3d  call    __scrt_is_nonwritable_in_current_image
0x140001b42  test    al, al
0x140001b44  jz      short loc_140001B57
0x140001b46  xor     r8d, r8d
0x140001b49  lea     edx, [r8+2]
0x140001b4d  xor     ecx, ecx
0x140001b4f  mov     rax, [rbx]
0x140001b52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001b57  call    __scrt_get_dyn_tls_dtor_callback
0x140001b5c  mov     rbx, rax
0x140001b5f  cmp     qword ptr [rax], 0
0x140001b63  jz      short loc_140001B79
0x140001b65  mov     rcx, rax
0x140001b68  call    __scrt_is_nonwritable_in_current_image
0x140001b6d  test    al, al
0x140001b6f  jz      short loc_140001B79
0x140001b71  mov     rcx, [rbx]; Callback
0x140001b74  call    _register_thread_local_exe_atexit_callback_0
0x140001b79  call    _get_initial_wide_environment
0x140001b7e  mov     rdi, rax
0x140001b81  call    __p___wargv
0x140001b86  mov     rbx, [rax]
0x140001b89  call    __p___argc
0x140001b8e  mov     r8, rdi
0x140001b91  mov     rdx, rbx
0x140001b94  mov     ecx, [rax]
0x140001b96  call    wmain
0x140001b9b  mov     ebx, eax
0x140001b9d  call    __scrt_is_managed_app
0x140001ba2  test    al, al
0x140001ba4  jz      short loc_140001BFB
0x140001ba6  test    sil, sil
0x140001ba9  jnz     short loc_140001BB0
0x140001bab  call    _o__cexit_0
0x140001bb0  xor     edx, edx
0x140001bb2  mov     cl, 1
0x140001bb4  call    __scrt_uninitialize_crt
0x140001bb9  mov     eax, ebx
0x140001bbb  jmp     short loc_140001BD6
0x140001bbd  mov     ebx, eax
0x140001bbf  call    __scrt_is_managed_app
0x140001bc4  test    al, al
0x140001bc6  jz      short loc_140001C03
0x140001bc8  cmp     [rsp+38h+var_18], 0
0x140001bcd  jnz     short loc_140001BD4
0x140001bcf  call    _c_exit_0
0x140001bd4  mov     eax, ebx
0x140001bd6  mov     rbx, [rsp+38h+arg_0]
0x140001bdb  mov     rsi, [rsp+38h+arg_8]
0x140001be0  add     rsp, 30h
0x140001be4  pop     rdi
0x140001be5  retn
0x140001be6  mov     ecx, 7
0x140001beb  call    __scrt_fastfail
0x140001bf1  mov     ecx, 7
0x140001bf6  call    __scrt_fastfail
0x140001bfb  mov     ecx, ebx; Code
0x140001bfd  call    _o_exit_0
0x140001c03  mov     ecx, ebx
0x140001c05  call    _o__exit_0
0x140001c0a  nop
0x14000c5cc  push    rbp
0x14000c5ce  sub     rsp, 20h
0x14000c5d2  mov     rbp, rdx
0x14000c5d5  mov     rdx, rcx; ExceptionPtr
0x14000c5d8  mov     rcx, [rcx]
0x14000c5db  mov     ecx, [rcx]; ExceptionNum
0x14000c5dd  call    _seh_filter_exe
0x14000c5e2  nop
0x14000c5e3  add     rsp, 20h
0x14000c5e7  pop     rbp
0x14000c5e8  retn
```
