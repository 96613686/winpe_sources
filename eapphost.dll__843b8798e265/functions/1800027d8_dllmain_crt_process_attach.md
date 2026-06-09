# dllmain_crt_process_attach

- ea: `0x1800027d8`
- end: `0x1800028d2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180002780`

## callees

- `0x1800027d8`
- `0x180002b4c`
- `0x180002b8c`
- `0x180002bc8`
- `0x180002cc8`
- `0x180002d9c`
- `0x180002e3c`
- `0x180002f20`
- `0x180003004`
- `0x180003028`
- `0x180003038`
- `0x180003044`
- `0x1800033a6`
- `0x1800033b2`
- `0x180039010`

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
  ++dword_18004F1D0;
  return 1;
}

```

## disassembly

```asm
0x1800027d8  push    rbx
0x1800027da  push    rsi
0x1800027db  push    rdi
0x1800027dc  push    r14
0x1800027de  sub     rsp, 28h
0x1800027e2  mov     rsi, rdx
0x1800027e5  mov     r14, rcx
0x1800027e8  xor     ecx, ecx
0x1800027ea  call    __scrt_initialize_crt
0x1800027ef  test    al, al
0x1800027f1  jz      loc_1800028BA
0x1800027f7  call    __scrt_acquire_startup_lock
0x1800027fc  mov     bl, al
0x1800027fe  mov     [rsp+48h+arg_10], al
0x180002802  mov     dil, 1
0x180002805  cmp     cs:__scrt_current_native_startup_state, 0
0x18000280c  jnz     loc_1800028C6
0x180002812  mov     cs:__scrt_current_native_startup_state, 1
0x18000281c  call    __scrt_dllmain_before_initialize_c
0x180002821  test    al, al
0x180002823  jz      short loc_180002874
0x180002825  call    _RTC_Initialize
0x18000282a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000282f  call    __scrt_initialize_default_local_stdio_options
0x180002834  lea     rdx, __xi_z; Last
0x18000283b  lea     rcx, __xi_a; First
0x180002842  call    _initterm_e_0
0x180002847  test    eax, eax
0x180002849  jnz     short loc_180002874
0x18000284b  call    __scrt_dllmain_after_initialize_c
0x180002850  test    al, al
0x180002852  jz      short loc_180002874
0x180002854  lea     rdx, __xc_z; Last
0x18000285b  lea     rcx, __xc_a; First
0x180002862  call    _initterm_0
0x180002867  mov     cs:__scrt_current_native_startup_state, 2
0x180002871  xor     dil, dil
0x180002874  mov     cl, bl
0x180002876  call    __scrt_release_startup_lock
0x18000287b  test    dil, dil
0x18000287e  jnz     short loc_1800028BA
0x180002880  call    __scrt_get_dyn_tls_init_callback
0x180002885  mov     rbx, rax
0x180002888  cmp     qword ptr [rax], 0
0x18000288c  jz      short loc_1800028AD
0x18000288e  mov     rcx, rax
0x180002891  call    __scrt_is_nonwritable_in_current_image
0x180002896  test    al, al
0x180002898  jz      short loc_1800028AD
0x18000289a  mov     r8, rsi
0x18000289d  mov     edx, 2
0x1800028a2  mov     rcx, r14
0x1800028a5  mov     rax, [rbx]
0x1800028a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028ad  inc     cs:dword_18004F1D0
0x1800028b3  mov     eax, 1
0x1800028b8  jmp     short loc_1800028BC
0x1800028ba  xor     eax, eax
0x1800028bc  add     rsp, 28h
0x1800028c0  pop     r14
0x1800028c2  pop     rdi
0x1800028c3  pop     rsi
0x1800028c4  pop     rbx
0x1800028c5  retn
0x1800028c6  mov     ecx, 7
0x1800028cb  call    __scrt_fastfail
0x1800351bc  push    rbp
0x1800351be  sub     rsp, 20h
0x1800351c2  mov     rbp, rdx
0x1800351c5  mov     cl, [rbp+60h]
0x1800351c8  add     rsp, 20h
0x1800351cc  pop     rbp
0x1800351cd  jmp     __scrt_release_startup_lock
```
