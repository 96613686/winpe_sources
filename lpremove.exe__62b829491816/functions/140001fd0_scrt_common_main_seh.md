# __scrt_common_main_seh

- ea: `0x140001fd0`
- end: `0x14000214b`
- name: `__scrt_common_main_seh`
- size: `379`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x140002160`

## callees

- `0x140001fd0`
- `0x14000223c`
- `0x14000227c`
- `0x140002350`
- `0x1400023f0`
- `0x14000241c`
- `0x1400025d0`
- `0x1400025e0`
- `0x1400025f0`
- `0x140002608`
- `0x140002a86`
- `0x140002a92`
- `0x140002a9e`
- `0x140002aaa`
- `0x140002ace`
- `0x140002ada`
- `0x140002b22`
- `0x140002b52`
- `0x140002b5e`
- `0x140002ba8`
- `0x140002bd8`
- `0x14000d8b8`
- `0x140011010`

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
0x140001fd0  mov     [rsp+arg_0], rbx
0x140001fd5  mov     [rsp+arg_8], rsi
0x140001fda  push    rdi
0x140001fdb  sub     rsp, 30h
0x140001fdf  mov     ecx, 1
0x140001fe4  call    __scrt_initialize_crt
0x140001fe9  test    al, al
0x140001feb  jz      loc_140002126
0x140001ff1  xor     sil, sil
0x140001ff4  mov     [rsp+38h+var_18], sil
0x140001ff9  call    __scrt_acquire_startup_lock
0x140001ffe  mov     bl, al
0x140002000  mov     ecx, cs:__scrt_current_native_startup_state
0x140002006  cmp     ecx, 1
0x140002009  jz      loc_140002131
0x14000200f  test    ecx, ecx
0x140002011  jnz     short loc_14000205D
0x140002013  mov     cs:__scrt_current_native_startup_state, 1
0x14000201d  lea     rdx, __xi_z; Last
0x140002024  lea     rcx, __xi_a; First
0x14000202b  call    _initterm_e_0
0x140002030  test    eax, eax
0x140002032  jz      short loc_14000203E
0x140002034  mov     eax, 0FFh
0x140002039  jmp     loc_140002116
0x14000203e  lea     rdx, __xc_z; Last
0x140002045  lea     rcx, __xc_a; First
0x14000204c  call    _initterm_0
0x140002051  mov     cs:__scrt_current_native_startup_state, 2
0x14000205b  jmp     short loc_140002065
0x14000205d  mov     sil, 1
0x140002060  mov     [rsp+38h+var_18], sil
0x140002065  mov     cl, bl
0x140002067  call    __scrt_release_startup_lock
0x14000206c  call    __scrt_get_dyn_tls_init_callback
0x140002071  mov     rbx, rax
0x140002074  cmp     qword ptr [rax], 0
0x140002078  jz      short loc_140002097
0x14000207a  mov     rcx, rax
0x14000207d  call    __scrt_is_nonwritable_in_current_image
0x140002082  test    al, al
0x140002084  jz      short loc_140002097
0x140002086  xor     r8d, r8d
0x140002089  lea     edx, [r8+2]
0x14000208d  xor     ecx, ecx
0x14000208f  mov     rax, [rbx]
0x140002092  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002097  call    __scrt_get_dyn_tls_dtor_callback
0x14000209c  mov     rbx, rax
0x14000209f  cmp     qword ptr [rax], 0
0x1400020a3  jz      short loc_1400020B9
0x1400020a5  mov     rcx, rax
0x1400020a8  call    __scrt_is_nonwritable_in_current_image
0x1400020ad  test    al, al
0x1400020af  jz      short loc_1400020B9
0x1400020b1  mov     rcx, [rbx]; Callback
0x1400020b4  call    _register_thread_local_exe_atexit_callback_0
0x1400020b9  call    _get_initial_wide_environment
0x1400020be  mov     rdi, rax
0x1400020c1  call    __p___wargv
0x1400020c6  mov     rbx, [rax]
0x1400020c9  call    __p___argc
0x1400020ce  mov     r8, rdi
0x1400020d1  mov     rdx, rbx
0x1400020d4  mov     ecx, [rax]
0x1400020d6  call    wmain
0x1400020db  mov     ebx, eax
0x1400020dd  call    __scrt_is_managed_app
0x1400020e2  test    al, al
0x1400020e4  jz      short loc_14000213B
0x1400020e6  test    sil, sil
0x1400020e9  jnz     short loc_1400020F0
0x1400020eb  call    _o__cexit_0
0x1400020f0  xor     edx, edx
0x1400020f2  mov     cl, 1
0x1400020f4  call    __scrt_uninitialize_crt
0x1400020f9  mov     eax, ebx
0x1400020fb  jmp     short loc_140002116
0x1400020fd  mov     ebx, eax
0x1400020ff  call    __scrt_is_managed_app
0x140002104  test    al, al
0x140002106  jz      short loc_140002143
0x140002108  cmp     [rsp+38h+var_18], 0
0x14000210d  jnz     short loc_140002114
0x14000210f  call    _c_exit_0
0x140002114  mov     eax, ebx
0x140002116  mov     rbx, [rsp+38h+arg_0]
0x14000211b  mov     rsi, [rsp+38h+arg_8]
0x140002120  add     rsp, 30h
0x140002124  pop     rdi
0x140002125  retn
0x140002126  mov     ecx, 7
0x14000212b  call    __scrt_fastfail
0x140002131  mov     ecx, 7
0x140002136  call    __scrt_fastfail
0x14000213b  mov     ecx, ebx; Code
0x14000213d  call    _o_exit_0
0x140002143  mov     ecx, ebx
0x140002145  call    _o__exit_0
0x14000214a  nop
0x14000febc  push    rbp
0x14000febe  sub     rsp, 20h
0x14000fec2  mov     rbp, rdx
0x14000fec5  mov     rdx, rcx; ExceptionPtr
0x14000fec8  mov     rcx, [rcx]
0x14000fecb  mov     ecx, [rcx]; ExceptionNum
0x14000fecd  call    _seh_filter_exe
0x14000fed2  nop
0x14000fed3  add     rsp, 20h
0x14000fed7  pop     rbp
0x14000fed8  retn
```
