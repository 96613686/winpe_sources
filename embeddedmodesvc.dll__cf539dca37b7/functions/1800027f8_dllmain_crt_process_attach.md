# dllmain_crt_process_attach

- ea: `0x1800027f8`
- end: `0x1800028f2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800027a0`

## callees

- `0x1800027f8`
- `0x180002b34`
- `0x180002b74`
- `0x180002bb0`
- `0x180002cb0`
- `0x180002d84`
- `0x180002e24`
- `0x18000304c`
- `0x180003074`
- `0x180003098`
- `0x1800030a8`
- `0x1800030b4`
- `0x180003476`
- `0x180003482`
- `0x18001b010`

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
  ++dword_180026310;
  return 1;
}

```

## disassembly

```asm
0x1800027f8  push    rbx
0x1800027fa  push    rsi
0x1800027fb  push    rdi
0x1800027fc  push    r14
0x1800027fe  sub     rsp, 28h
0x180002802  mov     rsi, rdx
0x180002805  mov     r14, rcx
0x180002808  xor     ecx, ecx
0x18000280a  call    __scrt_initialize_crt
0x18000280f  test    al, al
0x180002811  jz      loc_1800028DA
0x180002817  call    __scrt_acquire_startup_lock
0x18000281c  mov     bl, al
0x18000281e  mov     [rsp+48h+arg_10], al
0x180002822  mov     dil, 1
0x180002825  cmp     cs:__scrt_current_native_startup_state, 0
0x18000282c  jnz     loc_1800028E6
0x180002832  mov     cs:__scrt_current_native_startup_state, 1
0x18000283c  call    __scrt_dllmain_before_initialize_c
0x180002841  test    al, al
0x180002843  jz      short loc_180002894
0x180002845  call    _RTC_Initialize
0x18000284a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000284f  call    __scrt_initialize_default_local_stdio_options
0x180002854  lea     rdx, __xi_z; Last
0x18000285b  lea     rcx, __xi_a; First
0x180002862  call    _initterm_e_0
0x180002867  test    eax, eax
0x180002869  jnz     short loc_180002894
0x18000286b  call    __scrt_dllmain_after_initialize_c
0x180002870  test    al, al
0x180002872  jz      short loc_180002894
0x180002874  lea     rdx, __xc_z; Last
0x18000287b  lea     rcx, __xc_a; First
0x180002882  call    _initterm_0
0x180002887  mov     cs:__scrt_current_native_startup_state, 2
0x180002891  xor     dil, dil
0x180002894  mov     cl, bl
0x180002896  call    __scrt_release_startup_lock
0x18000289b  test    dil, dil
0x18000289e  jnz     short loc_1800028DA
0x1800028a0  call    __scrt_get_dyn_tls_init_callback
0x1800028a5  mov     rbx, rax
0x1800028a8  cmp     qword ptr [rax], 0
0x1800028ac  jz      short loc_1800028CD
0x1800028ae  mov     rcx, rax
0x1800028b1  call    __scrt_is_nonwritable_in_current_image
0x1800028b6  test    al, al
0x1800028b8  jz      short loc_1800028CD
0x1800028ba  mov     r8, rsi
0x1800028bd  mov     edx, 2
0x1800028c2  mov     rcx, r14
0x1800028c5  mov     rax, [rbx]
0x1800028c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028cd  inc     cs:dword_180026310
0x1800028d3  mov     eax, 1
0x1800028d8  jmp     short loc_1800028DC
0x1800028da  xor     eax, eax
0x1800028dc  add     rsp, 28h
0x1800028e0  pop     r14
0x1800028e2  pop     rdi
0x1800028e3  pop     rsi
0x1800028e4  pop     rbx
0x1800028e5  retn
0x1800028e6  mov     ecx, 7
0x1800028eb  call    __scrt_fastfail
0x1800187ec  push    rbp
0x1800187ee  sub     rsp, 20h
0x1800187f2  mov     rbp, rdx
0x1800187f5  mov     cl, [rbp+60h]
0x1800187f8  add     rsp, 20h
0x1800187fc  pop     rbp
0x1800187fd  jmp     __scrt_release_startup_lock
```
