# dllmain_crt_process_attach

- ea: `0x180004d08`
- end: `0x180004e02`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180004cb0`

## callees

- `0x180004d08`
- `0x180005044`
- `0x180005084`
- `0x1800050c0`
- `0x1800051c0`
- `0x180005294`
- `0x180005334`
- `0x1800055ec`
- `0x180005614`
- `0x180005638`
- `0x180005648`
- `0x180005654`
- `0x180005a26`
- `0x180005a32`
- `0x18000b010`

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
      if ( _scrt_dllmain_after_initialize_c() )
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
  ++dword_180012BF0;
  return 1;
}

```

## disassembly

```asm
0x180004d08  push    rbx
0x180004d0a  push    rsi
0x180004d0b  push    rdi
0x180004d0c  push    r14
0x180004d0e  sub     rsp, 28h
0x180004d12  mov     rsi, rdx
0x180004d15  mov     r14, rcx
0x180004d18  xor     ecx, ecx
0x180004d1a  call    __scrt_initialize_crt
0x180004d1f  test    al, al
0x180004d21  jz      loc_180004DEA
0x180004d27  call    __scrt_acquire_startup_lock
0x180004d2c  mov     bl, al
0x180004d2e  mov     [rsp+48h+arg_10], al
0x180004d32  mov     dil, 1
0x180004d35  cmp     cs:__scrt_current_native_startup_state, 0
0x180004d3c  jnz     loc_180004DF6
0x180004d42  mov     cs:__scrt_current_native_startup_state, 1
0x180004d4c  call    __scrt_dllmain_before_initialize_c
0x180004d51  test    al, al
0x180004d53  jz      short loc_180004DA4
0x180004d55  call    _RTC_Initialize
0x180004d5a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180004d5f  call    __scrt_initialize_default_local_stdio_options
0x180004d64  lea     rdx, __xi_z; Last
0x180004d6b  lea     rcx, __xi_a; First
0x180004d72  call    _initterm_e_0
0x180004d77  test    eax, eax
0x180004d79  jnz     short loc_180004DA4
0x180004d7b  call    __scrt_dllmain_after_initialize_c
0x180004d80  test    al, al
0x180004d82  jz      short loc_180004DA4
0x180004d84  lea     rdx, __xc_z; Last
0x180004d8b  lea     rcx, __xc_a; First
0x180004d92  call    _initterm_0
0x180004d97  mov     cs:__scrt_current_native_startup_state, 2
0x180004da1  xor     dil, dil
0x180004da4  mov     cl, bl
0x180004da6  call    __scrt_release_startup_lock
0x180004dab  test    dil, dil
0x180004dae  jnz     short loc_180004DEA
0x180004db0  call    __scrt_get_dyn_tls_init_callback
0x180004db5  mov     rbx, rax
0x180004db8  cmp     qword ptr [rax], 0
0x180004dbc  jz      short loc_180004DDD
0x180004dbe  mov     rcx, rax
0x180004dc1  call    __scrt_is_nonwritable_in_current_image
0x180004dc6  test    al, al
0x180004dc8  jz      short loc_180004DDD
0x180004dca  mov     r8, rsi
0x180004dcd  mov     edx, 2
0x180004dd2  mov     rcx, r14
0x180004dd5  mov     rax, [rbx]
0x180004dd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ddd  inc     cs:dword_180012BF0
0x180004de3  mov     eax, 1
0x180004de8  jmp     short loc_180004DEC
0x180004dea  xor     eax, eax
0x180004dec  add     rsp, 28h
0x180004df0  pop     r14
0x180004df2  pop     rdi
0x180004df3  pop     rsi
0x180004df4  pop     rbx
0x180004df5  retn
0x180004df6  mov     ecx, 7
0x180004dfb  call    __scrt_fastfail
0x18000aa54  push    rbp
0x18000aa56  sub     rsp, 20h
0x18000aa5a  mov     rbp, rdx
0x18000aa5d  mov     cl, [rbp+60h]
0x18000aa60  add     rsp, 20h
0x18000aa64  pop     rbp
0x18000aa65  jmp     __scrt_release_startup_lock
```
