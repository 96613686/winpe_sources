# dllmain_crt_process_attach

- ea: `0x18000d4d8`
- end: `0x18000d5d2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x18000d480`

## callees

- `0x18000d0c4`
- `0x18000d104`
- `0x18000d140`
- `0x18000d240`
- `0x18000d314`
- `0x18000d3b4`
- `0x18000d4d8`
- `0x18000db30`
- `0x18000dc04`
- `0x18000dc2c`
- `0x18000dc50`
- `0x18000dc60`
- `0x18000dce6`
- `0x18000dcf2`
- `0x180017010`

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
  ++dword_18001F594;
  return 1;
}

```

## disassembly

```asm
0x18000d4d8  push    rbx
0x18000d4da  push    rsi
0x18000d4db  push    rdi
0x18000d4dc  push    r14
0x18000d4de  sub     rsp, 28h
0x18000d4e2  mov     rsi, rdx
0x18000d4e5  mov     r14, rcx
0x18000d4e8  xor     ecx, ecx
0x18000d4ea  call    __scrt_initialize_crt
0x18000d4ef  test    al, al
0x18000d4f1  jz      loc_18000D5BA
0x18000d4f7  call    __scrt_acquire_startup_lock
0x18000d4fc  mov     bl, al
0x18000d4fe  mov     [rsp+48h+arg_10], al
0x18000d502  mov     dil, 1
0x18000d505  cmp     cs:__scrt_current_native_startup_state, 0
0x18000d50c  jnz     loc_18000D5C6
0x18000d512  mov     cs:__scrt_current_native_startup_state, 1
0x18000d51c  call    __scrt_dllmain_before_initialize_c
0x18000d521  test    al, al
0x18000d523  jz      short loc_18000D574
0x18000d525  call    _RTC_Initialize
0x18000d52a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000d52f  call    __scrt_initialize_default_local_stdio_options
0x18000d534  lea     rdx, __xi_z; Last
0x18000d53b  lea     rcx, __xi_a; First
0x18000d542  call    _initterm_e_0
0x18000d547  test    eax, eax
0x18000d549  jnz     short loc_18000D574
0x18000d54b  call    __scrt_dllmain_after_initialize_c
0x18000d550  test    al, al
0x18000d552  jz      short loc_18000D574
0x18000d554  lea     rdx, __xc_z; Last
0x18000d55b  lea     rcx, __xc_a; First
0x18000d562  call    _initterm_0
0x18000d567  mov     cs:__scrt_current_native_startup_state, 2
0x18000d571  xor     dil, dil
0x18000d574  mov     cl, bl
0x18000d576  call    __scrt_release_startup_lock
0x18000d57b  test    dil, dil
0x18000d57e  jnz     short loc_18000D5BA
0x18000d580  call    __scrt_get_dyn_tls_init_callback
0x18000d585  mov     rbx, rax
0x18000d588  cmp     qword ptr [rax], 0
0x18000d58c  jz      short loc_18000D5AD
0x18000d58e  mov     rcx, rax
0x18000d591  call    __scrt_is_nonwritable_in_current_image
0x18000d596  test    al, al
0x18000d598  jz      short loc_18000D5AD
0x18000d59a  mov     r8, rsi
0x18000d59d  mov     edx, 2
0x18000d5a2  mov     rcx, r14
0x18000d5a5  mov     rax, [rbx]
0x18000d5a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5ad  inc     cs:dword_18001F594
0x18000d5b3  mov     eax, 1
0x18000d5b8  jmp     short loc_18000D5BC
0x18000d5ba  xor     eax, eax
0x18000d5bc  add     rsp, 28h
0x18000d5c0  pop     r14
0x18000d5c2  pop     rdi
0x18000d5c3  pop     rsi
0x18000d5c4  pop     rbx
0x18000d5c5  retn
0x18000d5c6  mov     ecx, 7
0x18000d5cb  call    __scrt_fastfail
0x1800167da  push    rbp
0x1800167dc  sub     rsp, 20h
0x1800167e0  mov     rbp, rdx
0x1800167e3  mov     cl, [rbp+60h]
0x1800167e6  add     rsp, 20h
0x1800167ea  pop     rbp
0x1800167eb  jmp     __scrt_release_startup_lock
```
