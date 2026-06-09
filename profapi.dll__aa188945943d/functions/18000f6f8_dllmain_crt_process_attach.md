# dllmain_crt_process_attach

- ea: `0x18000f6f8`
- end: `0x18000f7f2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x18000f6a0`

## callees

- `0x18000f6f8`
- `0x18000fa34`
- `0x18000fa74`
- `0x18000fab0`
- `0x18000fbb0`
- `0x18000fc84`
- `0x18000fd24`
- `0x18000fed8`
- `0x18000ff00`
- `0x18000ff24`
- `0x18000ff34`
- `0x18000ff40`
- `0x1800102a6`
- `0x1800102b2`
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
  ++dword_180022230;
  return 1;
}

```

## disassembly

```asm
0x18000f6f8  push    rbx
0x18000f6fa  push    rsi
0x18000f6fb  push    rdi
0x18000f6fc  push    r14
0x18000f6fe  sub     rsp, 28h
0x18000f702  mov     rsi, rdx
0x18000f705  mov     r14, rcx
0x18000f708  xor     ecx, ecx
0x18000f70a  call    __scrt_initialize_crt
0x18000f70f  test    al, al
0x18000f711  jz      loc_18000F7DA
0x18000f717  call    __scrt_acquire_startup_lock
0x18000f71c  mov     bl, al
0x18000f71e  mov     [rsp+48h+arg_10], al
0x18000f722  mov     dil, 1
0x18000f725  cmp     cs:__scrt_current_native_startup_state, 0
0x18000f72c  jnz     loc_18000F7E6
0x18000f732  mov     cs:__scrt_current_native_startup_state, 1
0x18000f73c  call    __scrt_dllmain_before_initialize_c
0x18000f741  test    al, al
0x18000f743  jz      short loc_18000F794
0x18000f745  call    _RTC_Initialize
0x18000f74a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000f74f  call    __scrt_initialize_default_local_stdio_options
0x18000f754  lea     rdx, __xi_z; Last
0x18000f75b  lea     rcx, __xi_a; First
0x18000f762  call    _initterm_e_0
0x18000f767  test    eax, eax
0x18000f769  jnz     short loc_18000F794
0x18000f76b  call    __scrt_dllmain_after_initialize_c
0x18000f770  test    al, al
0x18000f772  jz      short loc_18000F794
0x18000f774  lea     rdx, __xc_z; Last
0x18000f77b  lea     rcx, __xc_a; First
0x18000f782  call    _initterm_0
0x18000f787  mov     cs:__scrt_current_native_startup_state, 2
0x18000f791  xor     dil, dil
0x18000f794  mov     cl, bl
0x18000f796  call    __scrt_release_startup_lock
0x18000f79b  test    dil, dil
0x18000f79e  jnz     short loc_18000F7DA
0x18000f7a0  call    __scrt_get_dyn_tls_init_callback
0x18000f7a5  mov     rbx, rax
0x18000f7a8  cmp     qword ptr [rax], 0
0x18000f7ac  jz      short loc_18000F7CD
0x18000f7ae  mov     rcx, rax
0x18000f7b1  call    __scrt_is_nonwritable_in_current_image
0x18000f7b6  test    al, al
0x18000f7b8  jz      short loc_18000F7CD
0x18000f7ba  mov     r8, rsi
0x18000f7bd  mov     edx, 2
0x18000f7c2  mov     rcx, r14
0x18000f7c5  mov     rax, [rbx]
0x18000f7c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7cd  inc     cs:dword_180022230
0x18000f7d3  mov     eax, 1
0x18000f7d8  jmp     short loc_18000F7DC
0x18000f7da  xor     eax, eax
0x18000f7dc  add     rsp, 28h
0x18000f7e0  pop     r14
0x18000f7e2  pop     rdi
0x18000f7e3  pop     rsi
0x18000f7e4  pop     rbx
0x18000f7e5  retn
0x18000f7e6  mov     ecx, 7
0x18000f7eb  call    __scrt_fastfail
0x1800171ce  push    rbp
0x1800171d0  sub     rsp, 20h
0x1800171d4  mov     rbp, rdx
0x1800171d7  mov     cl, [rbp+60h]
0x1800171da  add     rsp, 20h
0x1800171de  pop     rbp
0x1800171df  jmp     __scrt_release_startup_lock
```
