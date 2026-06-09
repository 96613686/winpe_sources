# dllmain_crt_process_attach

- ea: `0x1800027b8`
- end: `0x1800028b2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180002760`

## callees

- `0x1800027b8`
- `0x180002b38`
- `0x180002b78`
- `0x180002bb4`
- `0x180002cb4`
- `0x180002d88`
- `0x180002e28`
- `0x180003358`
- `0x180003380`
- `0x1800033a4`
- `0x1800033b4`
- `0x1800033c0`
- `0x1800034d6`
- `0x1800034e2`
- `0x180034010`

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
  ++dword_1800449B0;
  return 1;
}

```

## disassembly

```asm
0x1800027b8  push    rbx
0x1800027ba  push    rsi
0x1800027bb  push    rdi
0x1800027bc  push    r14
0x1800027be  sub     rsp, 28h
0x1800027c2  mov     rsi, rdx
0x1800027c5  mov     r14, rcx
0x1800027c8  xor     ecx, ecx
0x1800027ca  call    __scrt_initialize_crt
0x1800027cf  test    al, al
0x1800027d1  jz      loc_18000289A
0x1800027d7  call    __scrt_acquire_startup_lock
0x1800027dc  mov     bl, al
0x1800027de  mov     [rsp+48h+arg_10], al
0x1800027e2  mov     dil, 1
0x1800027e5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800027ec  jnz     loc_1800028A6
0x1800027f2  mov     cs:__scrt_current_native_startup_state, 1
0x1800027fc  call    __scrt_dllmain_before_initialize_c
0x180002801  test    al, al
0x180002803  jz      short loc_180002854
0x180002805  call    _RTC_Initialize
0x18000280a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000280f  call    __scrt_initialize_default_local_stdio_options
0x180002814  lea     rdx, __xi_z; Last
0x18000281b  lea     rcx, __xi_a; First
0x180002822  call    _initterm_e_0
0x180002827  test    eax, eax
0x180002829  jnz     short loc_180002854
0x18000282b  call    __scrt_dllmain_after_initialize_c
0x180002830  test    al, al
0x180002832  jz      short loc_180002854
0x180002834  lea     rdx, __xc_z; Last
0x18000283b  lea     rcx, __xc_a; First
0x180002842  call    _initterm_0
0x180002847  mov     cs:__scrt_current_native_startup_state, 2
0x180002851  xor     dil, dil
0x180002854  mov     cl, bl
0x180002856  call    __scrt_release_startup_lock
0x18000285b  test    dil, dil
0x18000285e  jnz     short loc_18000289A
0x180002860  call    __scrt_get_dyn_tls_init_callback
0x180002865  mov     rbx, rax
0x180002868  cmp     qword ptr [rax], 0
0x18000286c  jz      short loc_18000288D
0x18000286e  mov     rcx, rax
0x180002871  call    __scrt_is_nonwritable_in_current_image
0x180002876  test    al, al
0x180002878  jz      short loc_18000288D
0x18000287a  mov     r8, rsi
0x18000287d  mov     edx, 2
0x180002882  mov     rcx, r14
0x180002885  mov     rax, [rbx]
0x180002888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000288d  inc     cs:dword_1800449B0
0x180002893  mov     eax, 1
0x180002898  jmp     short loc_18000289C
0x18000289a  xor     eax, eax
0x18000289c  add     rsp, 28h
0x1800028a0  pop     r14
0x1800028a2  pop     rdi
0x1800028a3  pop     rsi
0x1800028a4  pop     rbx
0x1800028a5  retn
0x1800028a6  mov     ecx, 7
0x1800028ab  call    __scrt_fastfail
0x180031ebc  push    rbp
0x180031ebe  sub     rsp, 20h
0x180031ec2  mov     rbp, rdx
0x180031ec5  mov     cl, [rbp+60h]
0x180031ec8  add     rsp, 20h
0x180031ecc  pop     rbp
0x180031ecd  jmp     __scrt_release_startup_lock
```
