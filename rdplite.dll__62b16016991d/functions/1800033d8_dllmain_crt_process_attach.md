# dllmain_crt_process_attach

- ea: `0x1800033d8`
- end: `0x1800034d2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180003380`

## callees

- `0x1800033d8`
- `0x180003758`
- `0x180003798`
- `0x1800037d4`
- `0x1800038d4`
- `0x1800039a8`
- `0x180003a48`
- `0x180003c08`
- `0x180003c30`
- `0x180003c54`
- `0x180003c64`
- `0x180003c70`
- `0x180004016`
- `0x180004022`
- `0x18002a010`

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
  ++dword_18003C810;
  return 1;
}

```

## disassembly

```asm
0x1800033d8  push    rbx
0x1800033da  push    rsi
0x1800033db  push    rdi
0x1800033dc  push    r14
0x1800033de  sub     rsp, 28h
0x1800033e2  mov     rsi, rdx
0x1800033e5  mov     r14, rcx
0x1800033e8  xor     ecx, ecx
0x1800033ea  call    __scrt_initialize_crt
0x1800033ef  test    al, al
0x1800033f1  jz      loc_1800034BA
0x1800033f7  call    __scrt_acquire_startup_lock
0x1800033fc  mov     bl, al
0x1800033fe  mov     [rsp+48h+arg_10], al
0x180003402  mov     dil, 1
0x180003405  cmp     cs:__scrt_current_native_startup_state, 0
0x18000340c  jnz     loc_1800034C6
0x180003412  mov     cs:__scrt_current_native_startup_state, 1
0x18000341c  call    __scrt_dllmain_before_initialize_c
0x180003421  test    al, al
0x180003423  jz      short loc_180003474
0x180003425  call    _RTC_Initialize
0x18000342a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000342f  call    __scrt_initialize_default_local_stdio_options
0x180003434  lea     rdx, __xi_z; Last
0x18000343b  lea     rcx, __xi_a; First
0x180003442  call    _initterm_e_0
0x180003447  test    eax, eax
0x180003449  jnz     short loc_180003474
0x18000344b  call    __scrt_dllmain_after_initialize_c
0x180003450  test    al, al
0x180003452  jz      short loc_180003474
0x180003454  lea     rdx, __xc_z; Last
0x18000345b  lea     rcx, __xc_a; First
0x180003462  call    _initterm_0
0x180003467  mov     cs:__scrt_current_native_startup_state, 2
0x180003471  xor     dil, dil
0x180003474  mov     cl, bl
0x180003476  call    __scrt_release_startup_lock
0x18000347b  test    dil, dil
0x18000347e  jnz     short loc_1800034BA
0x180003480  call    __scrt_get_dyn_tls_init_callback
0x180003485  mov     rbx, rax
0x180003488  cmp     qword ptr [rax], 0
0x18000348c  jz      short loc_1800034AD
0x18000348e  mov     rcx, rax
0x180003491  call    __scrt_is_nonwritable_in_current_image
0x180003496  test    al, al
0x180003498  jz      short loc_1800034AD
0x18000349a  mov     r8, rsi
0x18000349d  mov     edx, 2
0x1800034a2  mov     rcx, r14
0x1800034a5  mov     rax, [rbx]
0x1800034a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034ad  inc     cs:dword_18003C810
0x1800034b3  mov     eax, 1
0x1800034b8  jmp     short loc_1800034BC
0x1800034ba  xor     eax, eax
0x1800034bc  add     rsp, 28h
0x1800034c0  pop     r14
0x1800034c2  pop     rdi
0x1800034c3  pop     rsi
0x1800034c4  pop     rbx
0x1800034c5  retn
0x1800034c6  mov     ecx, 7
0x1800034cb  call    __scrt_fastfail
0x1800283cc  push    rbp
0x1800283ce  sub     rsp, 20h
0x1800283d2  mov     rbp, rdx
0x1800283d5  mov     cl, [rbp+60h]
0x1800283d8  add     rsp, 20h
0x1800283dc  pop     rbp
0x1800283dd  jmp     __scrt_release_startup_lock
```
