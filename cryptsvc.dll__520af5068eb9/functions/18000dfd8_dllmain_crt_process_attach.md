# dllmain_crt_process_attach

- ea: `0x18000dfd8`
- end: `0x18000e0d2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x18000df80`

## callees

- `0x18000dfd8`
- `0x18000e3d0`
- `0x18000e3f8`
- `0x18000e41c`
- `0x18000e45c`
- `0x18000e498`
- `0x18000e598`
- `0x18000e66c`
- `0x18000e70c`
- `0x18000e7c8`
- `0x18000e7d8`
- `0x18000e7e4`
- `0x18000eb56`
- `0x18000eb62`
- `0x180018010`

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
  ++dword_180020170;
  return 1;
}

```

## disassembly

```asm
0x18000dfd8  push    rbx
0x18000dfda  push    rsi
0x18000dfdb  push    rdi
0x18000dfdc  push    r14
0x18000dfde  sub     rsp, 28h
0x18000dfe2  mov     rsi, rdx
0x18000dfe5  mov     r14, rcx
0x18000dfe8  xor     ecx, ecx
0x18000dfea  call    __scrt_initialize_crt
0x18000dfef  test    al, al
0x18000dff1  jz      loc_18000E0BA
0x18000dff7  call    __scrt_acquire_startup_lock
0x18000dffc  mov     bl, al
0x18000dffe  mov     [rsp+48h+arg_10], al
0x18000e002  mov     dil, 1
0x18000e005  cmp     cs:__scrt_current_native_startup_state, 0
0x18000e00c  jnz     loc_18000E0C6
0x18000e012  mov     cs:__scrt_current_native_startup_state, 1
0x18000e01c  call    __scrt_dllmain_before_initialize_c
0x18000e021  test    al, al
0x18000e023  jz      short loc_18000E074
0x18000e025  call    _RTC_Initialize
0x18000e02a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000e02f  call    __scrt_initialize_default_local_stdio_options
0x18000e034  lea     rdx, __xi_z; Last
0x18000e03b  lea     rcx, __xi_a; First
0x18000e042  call    _initterm_e_0
0x18000e047  test    eax, eax
0x18000e049  jnz     short loc_18000E074
0x18000e04b  call    __scrt_dllmain_after_initialize_c
0x18000e050  test    al, al
0x18000e052  jz      short loc_18000E074
0x18000e054  lea     rdx, __xc_z; Last
0x18000e05b  lea     rcx, __xc_a; First
0x18000e062  call    _initterm_0
0x18000e067  mov     cs:__scrt_current_native_startup_state, 2
0x18000e071  xor     dil, dil
0x18000e074  mov     cl, bl
0x18000e076  call    __scrt_release_startup_lock
0x18000e07b  test    dil, dil
0x18000e07e  jnz     short loc_18000E0BA
0x18000e080  call    __scrt_get_dyn_tls_init_callback
0x18000e085  mov     rbx, rax
0x18000e088  cmp     qword ptr [rax], 0
0x18000e08c  jz      short loc_18000E0AD
0x18000e08e  mov     rcx, rax
0x18000e091  call    __scrt_is_nonwritable_in_current_image
0x18000e096  test    al, al
0x18000e098  jz      short loc_18000E0AD
0x18000e09a  mov     r8, rsi
0x18000e09d  mov     edx, 2
0x18000e0a2  mov     rcx, r14
0x18000e0a5  mov     rax, [rbx]
0x18000e0a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0ad  inc     cs:dword_180020170
0x18000e0b3  mov     eax, 1
0x18000e0b8  jmp     short loc_18000E0BC
0x18000e0ba  xor     eax, eax
0x18000e0bc  add     rsp, 28h
0x18000e0c0  pop     r14
0x18000e0c2  pop     rdi
0x18000e0c3  pop     rsi
0x18000e0c4  pop     rbx
0x18000e0c5  retn
0x18000e0c6  mov     ecx, 7
0x18000e0cb  call    __scrt_fastfail
0x18001757c  push    rbp
0x18001757e  sub     rsp, 20h
0x180017582  mov     rbp, rdx
0x180017585  mov     cl, [rbp+60h]
0x180017588  add     rsp, 20h
0x18001758c  pop     rbp
0x18001758d  jmp     __scrt_release_startup_lock
```
