# dllmain_crt_process_attach

- ea: `0x1800013b8`
- end: `0x1800014b2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001360`

## callees

- `0x1800013b8`
- `0x1800016f4`
- `0x180001734`
- `0x180001770`
- `0x180001870`
- `0x180001944`
- `0x1800019e4`
- `0x180001cfc`
- `0x180001d24`
- `0x180001d48`
- `0x180001d58`
- `0x180001d64`
- `0x180002096`
- `0x1800020a2`
- `0x180022010`

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
  ++dword_18002A450;
  return 1;
}

```

## disassembly

```asm
0x1800013b8  push    rbx
0x1800013ba  push    rsi
0x1800013bb  push    rdi
0x1800013bc  push    r14
0x1800013be  sub     rsp, 28h
0x1800013c2  mov     rsi, rdx
0x1800013c5  mov     r14, rcx
0x1800013c8  xor     ecx, ecx
0x1800013ca  call    __scrt_initialize_crt
0x1800013cf  test    al, al
0x1800013d1  jz      loc_18000149A
0x1800013d7  call    __scrt_acquire_startup_lock
0x1800013dc  mov     bl, al
0x1800013de  mov     [rsp+48h+arg_10], al
0x1800013e2  mov     dil, 1
0x1800013e5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800013ec  jnz     loc_1800014A6
0x1800013f2  mov     cs:__scrt_current_native_startup_state, 1
0x1800013fc  call    __scrt_dllmain_before_initialize_c
0x180001401  test    al, al
0x180001403  jz      short loc_180001454
0x180001405  call    _RTC_Initialize
0x18000140a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000140f  call    __scrt_initialize_default_local_stdio_options
0x180001414  lea     rdx, __xi_z; Last
0x18000141b  lea     rcx, __xi_a; First
0x180001422  call    _initterm_e_0
0x180001427  test    eax, eax
0x180001429  jnz     short loc_180001454
0x18000142b  call    __scrt_dllmain_after_initialize_c
0x180001430  test    al, al
0x180001432  jz      short loc_180001454
0x180001434  lea     rdx, __xc_z; Last
0x18000143b  lea     rcx, __xc_a; First
0x180001442  call    _initterm_0
0x180001447  mov     cs:__scrt_current_native_startup_state, 2
0x180001451  xor     dil, dil
0x180001454  mov     cl, bl
0x180001456  call    __scrt_release_startup_lock
0x18000145b  test    dil, dil
0x18000145e  jnz     short loc_18000149A
0x180001460  call    __scrt_get_dyn_tls_init_callback
0x180001465  mov     rbx, rax
0x180001468  cmp     qword ptr [rax], 0
0x18000146c  jz      short loc_18000148D
0x18000146e  mov     rcx, rax
0x180001471  call    __scrt_is_nonwritable_in_current_image
0x180001476  test    al, al
0x180001478  jz      short loc_18000148D
0x18000147a  mov     r8, rsi
0x18000147d  mov     edx, 2
0x180001482  mov     rcx, r14
0x180001485  mov     rax, [rbx]
0x180001488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000148d  inc     cs:dword_18002A450
0x180001493  mov     eax, 1
0x180001498  jmp     short loc_18000149C
0x18000149a  xor     eax, eax
0x18000149c  add     rsp, 28h
0x1800014a0  pop     r14
0x1800014a2  pop     rdi
0x1800014a3  pop     rsi
0x1800014a4  pop     rbx
0x1800014a5  retn
0x1800014a6  mov     ecx, 7
0x1800014ab  call    __scrt_fastfail
0x18002183c  push    rbp
0x18002183e  sub     rsp, 20h
0x180021842  mov     rbp, rdx
0x180021845  mov     cl, [rbp+60h]
0x180021848  add     rsp, 20h
0x18002184c  pop     rbp
0x18002184d  jmp     __scrt_release_startup_lock
```
