# __scrt_common_main_seh

- ea: `0x140001ef0`
- end: `0x14000206b`
- name: `__scrt_common_main_seh`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x140002080`

## callees

- `0x140001ef0`
- `0x1400020d4`
- `0x140002114`
- `0x1400021e8`
- `0x140002288`
- `0x1400022b4`
- `0x1400024b0`
- `0x1400024c0`
- `0x1400024d0`
- `0x1400024e8`
- `0x140002936`
- `0x140002942`
- `0x14000294e`
- `0x14000295a`
- `0x14000297e`
- `0x14000298a`
- `0x1400029ea`
- `0x140002a1a`
- `0x140002a26`
- `0x140002a78`
- `0x140002ac0`
- `0x1400094c8`
- `0x140034010`

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
  v13 = wmain(*v12, (const unsigned __int16 **)v11);
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
0x140001ef0  mov     [rsp+arg_0], rbx
0x140001ef5  mov     [rsp+arg_8], rsi
0x140001efa  push    rdi
0x140001efb  sub     rsp, 30h
0x140001eff  mov     ecx, 1
0x140001f04  call    __scrt_initialize_crt
0x140001f09  test    al, al
0x140001f0b  jz      loc_140002046
0x140001f11  xor     sil, sil
0x140001f14  mov     [rsp+38h+var_18], sil
0x140001f19  call    __scrt_acquire_startup_lock
0x140001f1e  mov     bl, al
0x140001f20  mov     ecx, cs:__scrt_current_native_startup_state
0x140001f26  cmp     ecx, 1
0x140001f29  jz      loc_140002051
0x140001f2f  test    ecx, ecx
0x140001f31  jnz     short loc_140001F7D
0x140001f33  mov     cs:__scrt_current_native_startup_state, 1
0x140001f3d  lea     rdx, __xi_z; Last
0x140001f44  lea     rcx, __xi_a; First
0x140001f4b  call    _initterm_e_0
0x140001f50  test    eax, eax
0x140001f52  jz      short loc_140001F5E
0x140001f54  mov     eax, 0FFh
0x140001f59  jmp     loc_140002036
0x140001f5e  lea     rdx, __xc_z; Last
0x140001f65  lea     rcx, __xc_a; First
0x140001f6c  call    _initterm_0
0x140001f71  mov     cs:__scrt_current_native_startup_state, 2
0x140001f7b  jmp     short loc_140001F85
0x140001f7d  mov     sil, 1
0x140001f80  mov     [rsp+38h+var_18], sil
0x140001f85  mov     cl, bl
0x140001f87  call    __scrt_release_startup_lock
0x140001f8c  call    __scrt_get_dyn_tls_init_callback
0x140001f91  mov     rbx, rax
0x140001f94  cmp     qword ptr [rax], 0
0x140001f98  jz      short loc_140001FB7
0x140001f9a  mov     rcx, rax
0x140001f9d  call    __scrt_is_nonwritable_in_current_image
0x140001fa2  test    al, al
0x140001fa4  jz      short loc_140001FB7
0x140001fa6  xor     r8d, r8d
0x140001fa9  lea     edx, [r8+2]
0x140001fad  xor     ecx, ecx
0x140001faf  mov     rax, [rbx]
0x140001fb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001fb7  call    __scrt_get_dyn_tls_dtor_callback
0x140001fbc  mov     rbx, rax
0x140001fbf  cmp     qword ptr [rax], 0
0x140001fc3  jz      short loc_140001FD9
0x140001fc5  mov     rcx, rax
0x140001fc8  call    __scrt_is_nonwritable_in_current_image
0x140001fcd  test    al, al
0x140001fcf  jz      short loc_140001FD9
0x140001fd1  mov     rcx, [rbx]; Callback
0x140001fd4  call    _register_thread_local_exe_atexit_callback_0
0x140001fd9  call    _get_initial_wide_environment
0x140001fde  mov     rdi, rax
0x140001fe1  call    __p___wargv
0x140001fe6  mov     rbx, [rax]
0x140001fe9  call    __p___argc
0x140001fee  mov     r8, rdi
0x140001ff1  mov     rdx, rbx; unsigned __int16 **
0x140001ff4  mov     ecx, [rax]; unsigned int
0x140001ff6  call    wmain
0x140001ffb  mov     ebx, eax
0x140001ffd  call    __scrt_is_managed_app
0x140002002  test    al, al
0x140002004  jz      short loc_14000205B
0x140002006  test    sil, sil
0x140002009  jnz     short loc_140002010
0x14000200b  call    _o__cexit_0
0x140002010  xor     edx, edx
0x140002012  mov     cl, 1
0x140002014  call    __scrt_uninitialize_crt
0x140002019  mov     eax, ebx
0x14000201b  jmp     short loc_140002036
0x14000201d  mov     ebx, eax
0x14000201f  call    __scrt_is_managed_app
0x140002024  test    al, al
0x140002026  jz      short loc_140002063
0x140002028  cmp     [rsp+38h+var_18], 0
0x14000202d  jnz     short loc_140002034
0x14000202f  call    _c_exit_0
0x140002034  mov     eax, ebx
0x140002036  mov     rbx, [rsp+38h+arg_0]
0x14000203b  mov     rsi, [rsp+38h+arg_8]
0x140002040  add     rsp, 30h
0x140002044  pop     rdi
0x140002045  retn
0x140002046  mov     ecx, 7
0x14000204b  call    __scrt_fastfail
0x140002051  mov     ecx, 7
0x140002056  call    __scrt_fastfail
0x14000205b  mov     ecx, ebx; Code
0x14000205d  call    _o_exit_0
0x140002063  mov     ecx, ebx
0x140002065  call    _o__exit_0
0x14000206a  nop
0x14002e94c  push    rbp
0x14002e94e  sub     rsp, 20h
0x14002e952  mov     rbp, rdx
0x14002e955  mov     rdx, rcx; ExceptionPtr
0x14002e958  mov     rcx, [rcx]
0x14002e95b  mov     ecx, [rcx]; ExceptionNum
0x14002e95d  call    _seh_filter_exe
0x14002e962  nop
0x14002e963  add     rsp, 20h
0x14002e967  pop     rbp
0x14002e968  retn
```
