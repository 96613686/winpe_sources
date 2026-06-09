# dllmain_crt_process_attach

- ea: `0x1800013f8`
- end: `0x1800014f2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800013a0`

## callees

- `0x1800013f8`
- `0x180001734`
- `0x180001774`
- `0x1800017b0`
- `0x1800018b0`
- `0x180001984`
- `0x180001a24`
- `0x180001f00`
- `0x180001f28`
- `0x180001f4c`
- `0x180001f5c`
- `0x180001f68`
- `0x180002036`
- `0x180002042`
- `0x18002c010`

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
  ++dword_18003C528;
  return 1;
}

```

## disassembly

```asm
0x1800013f8  push    rbx
0x1800013fa  push    rsi
0x1800013fb  push    rdi
0x1800013fc  push    r14
0x1800013fe  sub     rsp, 28h
0x180001402  mov     rsi, rdx
0x180001405  mov     r14, rcx
0x180001408  xor     ecx, ecx
0x18000140a  call    __scrt_initialize_crt
0x18000140f  test    al, al
0x180001411  jz      loc_1800014DA
0x180001417  call    __scrt_acquire_startup_lock
0x18000141c  mov     bl, al
0x18000141e  mov     [rsp+48h+arg_10], al
0x180001422  mov     dil, 1
0x180001425  cmp     cs:__scrt_current_native_startup_state, 0
0x18000142c  jnz     loc_1800014E6
0x180001432  mov     cs:__scrt_current_native_startup_state, 1
0x18000143c  call    __scrt_dllmain_before_initialize_c
0x180001441  test    al, al
0x180001443  jz      short loc_180001494
0x180001445  call    _RTC_Initialize
0x18000144a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000144f  call    __scrt_initialize_default_local_stdio_options
0x180001454  lea     rdx, __xi_z; Last
0x18000145b  lea     rcx, __xi_a; First
0x180001462  call    _initterm_e_0
0x180001467  test    eax, eax
0x180001469  jnz     short loc_180001494
0x18000146b  call    __scrt_dllmain_after_initialize_c
0x180001470  test    al, al
0x180001472  jz      short loc_180001494
0x180001474  lea     rdx, __xc_z; Last
0x18000147b  lea     rcx, __xc_a; First
0x180001482  call    _initterm_0
0x180001487  mov     cs:__scrt_current_native_startup_state, 2
0x180001491  xor     dil, dil
0x180001494  mov     cl, bl
0x180001496  call    __scrt_release_startup_lock
0x18000149b  test    dil, dil
0x18000149e  jnz     short loc_1800014DA
0x1800014a0  call    __scrt_get_dyn_tls_init_callback
0x1800014a5  mov     rbx, rax
0x1800014a8  cmp     qword ptr [rax], 0
0x1800014ac  jz      short loc_1800014CD
0x1800014ae  mov     rcx, rax
0x1800014b1  call    __scrt_is_nonwritable_in_current_image
0x1800014b6  test    al, al
0x1800014b8  jz      short loc_1800014CD
0x1800014ba  mov     r8, rsi
0x1800014bd  mov     edx, 2
0x1800014c2  mov     rcx, r14
0x1800014c5  mov     rax, [rbx]
0x1800014c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014cd  inc     cs:dword_18003C528
0x1800014d3  mov     eax, 1
0x1800014d8  jmp     short loc_1800014DC
0x1800014da  xor     eax, eax
0x1800014dc  add     rsp, 28h
0x1800014e0  pop     r14
0x1800014e2  pop     rdi
0x1800014e3  pop     rsi
0x1800014e4  pop     rbx
0x1800014e5  retn
0x1800014e6  mov     ecx, 7
0x1800014eb  call    __scrt_fastfail
0x18002b03c  push    rbp
0x18002b03e  sub     rsp, 20h
0x18002b042  mov     rbp, rdx
0x18002b045  mov     cl, [rbp+60h]
0x18002b048  add     rsp, 20h
0x18002b04c  pop     rbp
0x18002b04d  jmp     __scrt_release_startup_lock
```
