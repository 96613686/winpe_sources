# __scrt_common_main_seh

- ea: `0x1400012b0`
- end: `0x14000142b`
- name: `__scrt_common_main_seh`
- size: `379`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x140001440`

## callees

- `0x1400012b0`
- `0x1400014d8`
- `0x140001518`
- `0x1400015ec`
- `0x14000168c`
- `0x1400016b8`
- `0x1400018c0`
- `0x1400018d0`
- `0x1400018e0`
- `0x1400018f8`
- `0x140001d76`
- `0x140001d82`
- `0x140001d8e`
- `0x140001d9a`
- `0x140001dbe`
- `0x140001dca`
- `0x140001e12`
- `0x140001e42`
- `0x140001e4e`
- `0x140001e8a`
- `0x140001eba`
- `0x140007018`
- `0x140008010`

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
  unsigned int v11; // ebx
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
0x1400012b0  mov     [rsp+arg_0], rbx
0x1400012b5  mov     [rsp+arg_8], rsi
0x1400012ba  push    rdi
0x1400012bb  sub     rsp, 30h
0x1400012bf  mov     ecx, 1
0x1400012c4  call    __scrt_initialize_crt
0x1400012c9  test    al, al
0x1400012cb  jz      loc_140001406
0x1400012d1  xor     sil, sil
0x1400012d4  mov     [rsp+38h+var_18], sil
0x1400012d9  call    __scrt_acquire_startup_lock
0x1400012de  mov     bl, al
0x1400012e0  mov     ecx, cs:__scrt_current_native_startup_state
0x1400012e6  cmp     ecx, 1
0x1400012e9  jz      loc_140001411
0x1400012ef  test    ecx, ecx
0x1400012f1  jnz     short loc_14000133D
0x1400012f3  mov     cs:__scrt_current_native_startup_state, 1
0x1400012fd  lea     rdx, __xi_z; Last
0x140001304  lea     rcx, __xi_a; First
0x14000130b  call    _initterm_e_0
0x140001310  test    eax, eax
0x140001312  jz      short loc_14000131E
0x140001314  mov     eax, 0FFh
0x140001319  jmp     loc_1400013F6
0x14000131e  lea     rdx, __xc_z; Last
0x140001325  lea     rcx, __xc_a; First
0x14000132c  call    _initterm_0
0x140001331  mov     cs:__scrt_current_native_startup_state, 2
0x14000133b  jmp     short loc_140001345
0x14000133d  mov     sil, 1
0x140001340  mov     [rsp+38h+var_18], sil
0x140001345  mov     cl, bl
0x140001347  call    __scrt_release_startup_lock
0x14000134c  call    __scrt_get_dyn_tls_init_callback
0x140001351  mov     rbx, rax
0x140001354  cmp     qword ptr [rax], 0
0x140001358  jz      short loc_140001377
0x14000135a  mov     rcx, rax
0x14000135d  call    __scrt_is_nonwritable_in_current_image
0x140001362  test    al, al
0x140001364  jz      short loc_140001377
0x140001366  xor     r8d, r8d
0x140001369  lea     edx, [r8+2]
0x14000136d  xor     ecx, ecx
0x14000136f  mov     rax, [rbx]
0x140001372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001377  call    __scrt_get_dyn_tls_dtor_callback
0x14000137c  mov     rbx, rax
0x14000137f  cmp     qword ptr [rax], 0
0x140001383  jz      short loc_140001399
0x140001385  mov     rcx, rax
0x140001388  call    __scrt_is_nonwritable_in_current_image
0x14000138d  test    al, al
0x14000138f  jz      short loc_140001399
0x140001391  mov     rcx, [rbx]; Callback
0x140001394  call    _register_thread_local_exe_atexit_callback_0
0x140001399  call    _get_initial_wide_environment
0x14000139e  mov     rdi, rax
0x1400013a1  call    __p___wargv
0x1400013a6  mov     rbx, [rax]
0x1400013a9  call    __p___argc
0x1400013ae  mov     r8, rdi
0x1400013b1  mov     rdx, rbx
0x1400013b4  mov     ecx, [rax]
0x1400013b6  call    wmain
0x1400013bb  mov     ebx, eax
0x1400013bd  call    __scrt_is_managed_app
0x1400013c2  test    al, al
0x1400013c4  jz      short loc_14000141B
0x1400013c6  test    sil, sil
0x1400013c9  jnz     short loc_1400013D0
0x1400013cb  call    _o__cexit_0
0x1400013d0  xor     edx, edx
0x1400013d2  mov     cl, 1
0x1400013d4  call    __scrt_uninitialize_crt
0x1400013d9  mov     eax, ebx
0x1400013db  jmp     short loc_1400013F6
0x1400013dd  mov     ebx, eax
0x1400013df  call    __scrt_is_managed_app
0x1400013e4  test    al, al
0x1400013e6  jz      short loc_140001423
0x1400013e8  cmp     [rsp+38h+var_18], 0
0x1400013ed  jnz     short loc_1400013F4
0x1400013ef  call    _c_exit_0
0x1400013f4  mov     eax, ebx
0x1400013f6  mov     rbx, [rsp+38h+arg_0]
0x1400013fb  mov     rsi, [rsp+38h+arg_8]
0x140001400  add     rsp, 30h
0x140001404  pop     rdi
0x140001405  retn
0x140001406  mov     ecx, 7
0x14000140b  call    __scrt_fastfail
0x140001411  mov     ecx, 7
0x140001416  call    __scrt_fastfail
0x14000141b  mov     ecx, ebx; Code
0x14000141d  call    _o_exit_0
0x140001423  mov     ecx, ebx
0x140001425  call    _o__exit_0
0x14000142a  nop
0x14000795c  push    rbp
0x14000795e  sub     rsp, 20h
0x140007962  mov     rbp, rdx
0x140007965  mov     rdx, rcx; ExceptionPtr
0x140007968  mov     rcx, [rcx]
0x14000796b  mov     ecx, [rcx]; ExceptionNum
0x14000796d  call    _seh_filter_exe
0x140007972  nop
0x140007973  add     rsp, 20h
0x140007977  pop     rbp
0x140007978  retn
```
