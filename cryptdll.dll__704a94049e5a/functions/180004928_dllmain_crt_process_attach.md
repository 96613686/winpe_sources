# dllmain_crt_process_attach

- ea: `0x180004928`
- end: `0x180004a22`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800048d0`

## callees

- `0x180004928`
- `0x180004d20`
- `0x180004d48`
- `0x180004d6c`
- `0x180004dac`
- `0x180004de8`
- `0x180004ee8`
- `0x180004fbc`
- `0x18000505c`
- `0x1800050b8`
- `0x1800050c8`
- `0x1800050d4`
- `0x180005446`
- `0x180005452`
- `0x180009010`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_attach(__int64 a1, __int64 a2)
{
  char v4; // bl
  char v5; // di
  __int64 v6; // rcx
  void (__fastcall **dyn_tls_init_callback)(__int64, __int64, __int64); // rax
  void (__fastcall **v8)(__int64, __int64, __int64); // rbx

  if ( !(unsigned __int8)_scrt_initialize_crt(0) )
    return 0;
  v4 = _scrt_acquire_startup_lock();
  v5 = 1;
  if ( _scrt_current_native_startup_state )
    _scrt_fastfail(7);
  _scrt_current_native_startup_state = 1;
  if ( (unsigned __int8)_scrt_dllmain_before_initialize_c() )
  {
    RTC_Initialize();
    __scrt_initialize_type_info();
    _scrt_initialize_default_local_stdio_options();
    if ( !initterm_e_0((_PIFV *)&_xi_a, (_PIFV *)&_xi_z) )
    {
      if ( (unsigned __int8)_scrt_dllmain_after_initialize_c() )
      {
        initterm_0((_PVFV *)&_xc_a, (_PVFV *)&_xc_z);
        _scrt_current_native_startup_state = 2;
        v5 = 0;
      }
    }
  }
  LOBYTE(v6) = v4;
  _scrt_release_startup_lock(v6);
  if ( v5 )
    return 0;
  dyn_tls_init_callback = (void (__fastcall **)(__int64, __int64, __int64))_scrt_get_dyn_tls_init_callback();
  v8 = dyn_tls_init_callback;
  if ( *dyn_tls_init_callback )
  {
    if ( (unsigned __int8)_scrt_is_nonwritable_in_current_image(dyn_tls_init_callback) )
      (*v8)(a1, 2, a2);
  }
  ++dword_18000E510;
  return 1;
}

```

## disassembly

```asm
0x180004928  push    rbx
0x18000492a  push    rsi
0x18000492b  push    rdi
0x18000492c  push    r14
0x18000492e  sub     rsp, 28h
0x180004932  mov     rsi, rdx
0x180004935  mov     r14, rcx
0x180004938  xor     ecx, ecx
0x18000493a  call    __scrt_initialize_crt
0x18000493f  test    al, al
0x180004941  jz      loc_180004A0A
0x180004947  call    __scrt_acquire_startup_lock
0x18000494c  mov     bl, al
0x18000494e  mov     [rsp+48h+arg_10], al
0x180004952  mov     dil, 1
0x180004955  cmp     cs:__scrt_current_native_startup_state, 0
0x18000495c  jnz     loc_180004A16
0x180004962  mov     cs:__scrt_current_native_startup_state, 1
0x18000496c  call    __scrt_dllmain_before_initialize_c
0x180004971  test    al, al
0x180004973  jz      short loc_1800049C4
0x180004975  call    _RTC_Initialize
0x18000497a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000497f  call    __scrt_initialize_default_local_stdio_options
0x180004984  lea     rdx, __xi_z; Last
0x18000498b  lea     rcx, __xi_a; First
0x180004992  call    _initterm_e_0
0x180004997  test    eax, eax
0x180004999  jnz     short loc_1800049C4
0x18000499b  call    __scrt_dllmain_after_initialize_c
0x1800049a0  test    al, al
0x1800049a2  jz      short loc_1800049C4
0x1800049a4  lea     rdx, __xc_z; Last
0x1800049ab  lea     rcx, __xc_a; First
0x1800049b2  call    _initterm_0
0x1800049b7  mov     cs:__scrt_current_native_startup_state, 2
0x1800049c1  xor     dil, dil
0x1800049c4  mov     cl, bl
0x1800049c6  call    __scrt_release_startup_lock
0x1800049cb  test    dil, dil
0x1800049ce  jnz     short loc_180004A0A
0x1800049d0  call    __scrt_get_dyn_tls_init_callback
0x1800049d5  mov     rbx, rax
0x1800049d8  cmp     qword ptr [rax], 0
0x1800049dc  jz      short loc_1800049FD
0x1800049de  mov     rcx, rax
0x1800049e1  call    __scrt_is_nonwritable_in_current_image
0x1800049e6  test    al, al
0x1800049e8  jz      short loc_1800049FD
0x1800049ea  mov     r8, rsi
0x1800049ed  mov     edx, 2
0x1800049f2  mov     rcx, r14
0x1800049f5  mov     rax, [rbx]
0x1800049f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049fd  inc     cs:dword_18000E510
0x180004a03  mov     eax, 1
0x180004a08  jmp     short loc_180004A0C
0x180004a0a  xor     eax, eax
0x180004a0c  add     rsp, 28h
0x180004a10  pop     r14
0x180004a12  pop     rdi
0x180004a13  pop     rsi
0x180004a14  pop     rbx
0x180004a15  retn
0x180004a16  mov     ecx, 7
0x180004a1b  call    __scrt_fastfail
0x18000849c  push    rbp
0x18000849e  sub     rsp, 20h
0x1800084a2  mov     rbp, rdx
0x1800084a5  mov     cl, [rbp+60h]
0x1800084a8  add     rsp, 20h
0x1800084ac  pop     rbp
0x1800084ad  jmp     __scrt_release_startup_lock
```
