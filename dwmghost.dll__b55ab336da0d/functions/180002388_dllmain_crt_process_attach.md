# dllmain_crt_process_attach

- ea: `0x180002388`
- end: `0x180002482`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180002330`

## callees

- `0x1800011b4`
- `0x1800011f4`
- `0x180001230`
- `0x180001330`
- `0x180001404`
- `0x1800014a4`
- `0x1800018b4`
- `0x180002388`
- `0x180002744`
- `0x18000276c`
- `0x180002790`
- `0x1800027a0`
- `0x180002825`
- `0x180002831`
- `0x18000c010`

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
  ++dword_180012240;
  return 1;
}

```

## disassembly

```asm
0x180002388  push    rbx
0x18000238a  push    rsi
0x18000238b  push    rdi
0x18000238c  push    r14
0x18000238e  sub     rsp, 28h
0x180002392  mov     rsi, rdx
0x180002395  mov     r14, rcx
0x180002398  xor     ecx, ecx
0x18000239a  call    __scrt_initialize_crt
0x18000239f  test    al, al
0x1800023a1  jz      loc_18000246A
0x1800023a7  call    __scrt_acquire_startup_lock
0x1800023ac  mov     bl, al
0x1800023ae  mov     [rsp+48h+arg_10], al
0x1800023b2  mov     dil, 1
0x1800023b5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800023bc  jnz     loc_180002476
0x1800023c2  mov     cs:__scrt_current_native_startup_state, 1
0x1800023cc  call    __scrt_dllmain_before_initialize_c
0x1800023d1  test    al, al
0x1800023d3  jz      short loc_180002424
0x1800023d5  call    _RTC_Initialize
0x1800023da  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800023df  call    __scrt_initialize_default_local_stdio_options
0x1800023e4  lea     rdx, __xi_z; Last
0x1800023eb  lea     rcx, __xi_a; First
0x1800023f2  call    _initterm_e_0
0x1800023f7  test    eax, eax
0x1800023f9  jnz     short loc_180002424
0x1800023fb  call    __scrt_dllmain_after_initialize_c
0x180002400  test    al, al
0x180002402  jz      short loc_180002424
0x180002404  lea     rdx, __xc_z; Last
0x18000240b  lea     rcx, __xc_a; First
0x180002412  call    _initterm_0
0x180002417  mov     cs:__scrt_current_native_startup_state, 2
0x180002421  xor     dil, dil
0x180002424  mov     cl, bl
0x180002426  call    __scrt_release_startup_lock
0x18000242b  test    dil, dil
0x18000242e  jnz     short loc_18000246A
0x180002430  call    __scrt_get_dyn_tls_init_callback
0x180002435  mov     rbx, rax
0x180002438  cmp     qword ptr [rax], 0
0x18000243c  jz      short loc_18000245D
0x18000243e  mov     rcx, rax
0x180002441  call    __scrt_is_nonwritable_in_current_image
0x180002446  test    al, al
0x180002448  jz      short loc_18000245D
0x18000244a  mov     r8, rsi
0x18000244d  mov     edx, 2
0x180002452  mov     rcx, r14
0x180002455  mov     rax, [rbx]
0x180002458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000245d  inc     cs:dword_180012240
0x180002463  mov     eax, 1
0x180002468  jmp     short loc_18000246C
0x18000246a  xor     eax, eax
0x18000246c  add     rsp, 28h
0x180002470  pop     r14
0x180002472  pop     rdi
0x180002473  pop     rsi
0x180002474  pop     rbx
0x180002475  retn
0x180002476  mov     ecx, 7
0x18000247b  call    __scrt_fastfail
0x18000b46a  push    rbp
0x18000b46c  sub     rsp, 20h
0x18000b470  mov     rbp, rdx
0x18000b473  mov     cl, [rbp+60h]
0x18000b476  add     rsp, 20h
0x18000b47a  pop     rbp
0x18000b47b  jmp     __scrt_release_startup_lock
```
