# dllmain_crt_process_attach

- ea: `0x180001898`
- end: `0x180001992`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001840`

## callees

- `0x180001898`
- `0x180001c7c`
- `0x180001cbc`
- `0x180001cf8`
- `0x180001df8`
- `0x180001ecc`
- `0x180001f6c`
- `0x1800021e4`
- `0x18000220c`
- `0x180002230`
- `0x180002240`
- `0x18000224c`
- `0x180002616`
- `0x180002622`
- `0x18002d010`

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
  ++dword_18003DD90;
  return 1;
}

```

## disassembly

```asm
0x180001898  push    rbx
0x18000189a  push    rsi
0x18000189b  push    rdi
0x18000189c  push    r14
0x18000189e  sub     rsp, 28h
0x1800018a2  mov     rsi, rdx
0x1800018a5  mov     r14, rcx
0x1800018a8  xor     ecx, ecx
0x1800018aa  call    __scrt_initialize_crt
0x1800018af  test    al, al
0x1800018b1  jz      loc_18000197A
0x1800018b7  call    __scrt_acquire_startup_lock
0x1800018bc  mov     bl, al
0x1800018be  mov     [rsp+48h+arg_10], al
0x1800018c2  mov     dil, 1
0x1800018c5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800018cc  jnz     loc_180001986
0x1800018d2  mov     cs:__scrt_current_native_startup_state, 1
0x1800018dc  call    __scrt_dllmain_before_initialize_c
0x1800018e1  test    al, al
0x1800018e3  jz      short loc_180001934
0x1800018e5  call    _RTC_Initialize
0x1800018ea  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800018ef  call    __scrt_initialize_default_local_stdio_options
0x1800018f4  lea     rdx, __xi_z; Last
0x1800018fb  lea     rcx, __xi_a; First
0x180001902  call    _initterm_e_0
0x180001907  test    eax, eax
0x180001909  jnz     short loc_180001934
0x18000190b  call    __scrt_dllmain_after_initialize_c
0x180001910  test    al, al
0x180001912  jz      short loc_180001934
0x180001914  lea     rdx, __xc_z; Last
0x18000191b  lea     rcx, __xc_a; First
0x180001922  call    _initterm_0
0x180001927  mov     cs:__scrt_current_native_startup_state, 2
0x180001931  xor     dil, dil
0x180001934  mov     cl, bl
0x180001936  call    __scrt_release_startup_lock
0x18000193b  test    dil, dil
0x18000193e  jnz     short loc_18000197A
0x180001940  call    __scrt_get_dyn_tls_init_callback
0x180001945  mov     rbx, rax
0x180001948  cmp     qword ptr [rax], 0
0x18000194c  jz      short loc_18000196D
0x18000194e  mov     rcx, rax
0x180001951  call    __scrt_is_nonwritable_in_current_image
0x180001956  test    al, al
0x180001958  jz      short loc_18000196D
0x18000195a  mov     r8, rsi
0x18000195d  mov     edx, 2
0x180001962  mov     rcx, r14
0x180001965  mov     rax, [rbx]
0x180001968  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000196d  inc     cs:dword_18003DD90
0x180001973  mov     eax, 1
0x180001978  jmp     short loc_18000197C
0x18000197a  xor     eax, eax
0x18000197c  add     rsp, 28h
0x180001980  pop     r14
0x180001982  pop     rdi
0x180001983  pop     rsi
0x180001984  pop     rbx
0x180001985  retn
0x180001986  mov     ecx, 7
0x18000198b  call    __scrt_fastfail
0x18002c2bc  push    rbp
0x18002c2be  sub     rsp, 20h
0x18002c2c2  mov     rbp, rdx
0x18002c2c5  mov     cl, [rbp+60h]
0x18002c2c8  add     rsp, 20h
0x18002c2cc  pop     rbp
0x18002c2cd  jmp     __scrt_release_startup_lock
```
