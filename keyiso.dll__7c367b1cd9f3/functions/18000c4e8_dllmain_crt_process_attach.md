# dllmain_crt_process_attach

- ea: `0x18000c4e8`
- end: `0x18000c5e2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x18000c490`

## callees

- `0x18000c4e8`
- `0x18000c7f4`
- `0x18000c834`
- `0x18000c870`
- `0x18000c970`
- `0x18000ca44`
- `0x18000cae4`
- `0x18000cbdc`
- `0x18000cc04`
- `0x18000cc28`
- `0x18000cc38`
- `0x18000cc44`
- `0x18000cf96`
- `0x18000cfa2`
- `0x180019010`

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
  ++dword_180025920;
  return 1;
}

```

## disassembly

```asm
0x18000c4e8  push    rbx
0x18000c4ea  push    rsi
0x18000c4eb  push    rdi
0x18000c4ec  push    r14
0x18000c4ee  sub     rsp, 28h
0x18000c4f2  mov     rsi, rdx
0x18000c4f5  mov     r14, rcx
0x18000c4f8  xor     ecx, ecx
0x18000c4fa  call    __scrt_initialize_crt
0x18000c4ff  test    al, al
0x18000c501  jz      loc_18000C5CA
0x18000c507  call    __scrt_acquire_startup_lock
0x18000c50c  mov     bl, al
0x18000c50e  mov     [rsp+48h+arg_10], al
0x18000c512  mov     dil, 1
0x18000c515  cmp     cs:__scrt_current_native_startup_state, 0
0x18000c51c  jnz     loc_18000C5D6
0x18000c522  mov     cs:__scrt_current_native_startup_state, 1
0x18000c52c  call    __scrt_dllmain_before_initialize_c
0x18000c531  test    al, al
0x18000c533  jz      short loc_18000C584
0x18000c535  call    _RTC_Initialize
0x18000c53a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000c53f  call    __scrt_initialize_default_local_stdio_options
0x18000c544  lea     rdx, __xi_z; Last
0x18000c54b  lea     rcx, __xi_a; First
0x18000c552  call    _initterm_e_0
0x18000c557  test    eax, eax
0x18000c559  jnz     short loc_18000C584
0x18000c55b  call    __scrt_dllmain_after_initialize_c
0x18000c560  test    al, al
0x18000c562  jz      short loc_18000C584
0x18000c564  lea     rdx, __xc_z; Last
0x18000c56b  lea     rcx, __xc_a; First
0x18000c572  call    _initterm_0
0x18000c577  mov     cs:__scrt_current_native_startup_state, 2
0x18000c581  xor     dil, dil
0x18000c584  mov     cl, bl
0x18000c586  call    __scrt_release_startup_lock
0x18000c58b  test    dil, dil
0x18000c58e  jnz     short loc_18000C5CA
0x18000c590  call    __scrt_get_dyn_tls_init_callback
0x18000c595  mov     rbx, rax
0x18000c598  cmp     qword ptr [rax], 0
0x18000c59c  jz      short loc_18000C5BD
0x18000c59e  mov     rcx, rax
0x18000c5a1  call    __scrt_is_nonwritable_in_current_image
0x18000c5a6  test    al, al
0x18000c5a8  jz      short loc_18000C5BD
0x18000c5aa  mov     r8, rsi
0x18000c5ad  mov     edx, 2
0x18000c5b2  mov     rcx, r14
0x18000c5b5  mov     rax, [rbx]
0x18000c5b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5bd  inc     cs:dword_180025920
0x18000c5c3  mov     eax, 1
0x18000c5c8  jmp     short loc_18000C5CC
0x18000c5ca  xor     eax, eax
0x18000c5cc  add     rsp, 28h
0x18000c5d0  pop     r14
0x18000c5d2  pop     rdi
0x18000c5d3  pop     rsi
0x18000c5d4  pop     rbx
0x18000c5d5  retn
0x18000c5d6  mov     ecx, 7
0x18000c5db  call    __scrt_fastfail
0x180018a19  push    rbp
0x180018a1b  sub     rsp, 20h
0x180018a1f  mov     rbp, rdx
0x180018a22  mov     cl, [rbp+60h]
0x180018a25  add     rsp, 20h
0x180018a29  pop     rbp
0x180018a2a  jmp     __scrt_release_startup_lock
```
