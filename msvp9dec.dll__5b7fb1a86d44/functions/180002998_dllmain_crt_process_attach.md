# dllmain_crt_process_attach

- ea: `0x180002998`
- end: `0x180002a92`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180002940`

## callees

- `0x180002998`
- `0x180002cf8`
- `0x180002d38`
- `0x180002d74`
- `0x180002e74`
- `0x180002f48`
- `0x180002fe8`
- `0x18000316c`
- `0x180003194`
- `0x1800031b8`
- `0x1800031c8`
- `0x1800031d4`
- `0x18000379c`
- `0x1800037a8`
- `0x180006010`

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
  ++dword_18000A1D0;
  return 1;
}

```

## disassembly

```asm
0x180002998  push    rbx
0x18000299a  push    rsi
0x18000299b  push    rdi
0x18000299c  push    r14
0x18000299e  sub     rsp, 28h
0x1800029a2  mov     rsi, rdx
0x1800029a5  mov     r14, rcx
0x1800029a8  xor     ecx, ecx
0x1800029aa  call    __scrt_initialize_crt
0x1800029af  test    al, al
0x1800029b1  jz      loc_180002A7A
0x1800029b7  call    __scrt_acquire_startup_lock
0x1800029bc  mov     bl, al
0x1800029be  mov     [rsp+48h+arg_10], al
0x1800029c2  mov     dil, 1
0x1800029c5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800029cc  jnz     loc_180002A86
0x1800029d2  mov     cs:__scrt_current_native_startup_state, 1
0x1800029dc  call    __scrt_dllmain_before_initialize_c
0x1800029e1  test    al, al
0x1800029e3  jz      short loc_180002A34
0x1800029e5  call    _RTC_Initialize
0x1800029ea  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800029ef  call    __scrt_initialize_default_local_stdio_options
0x1800029f4  lea     rdx, __xi_z; Last
0x1800029fb  lea     rcx, __xi_a; First
0x180002a02  call    _initterm_e_0
0x180002a07  test    eax, eax
0x180002a09  jnz     short loc_180002A34
0x180002a0b  call    __scrt_dllmain_after_initialize_c
0x180002a10  test    al, al
0x180002a12  jz      short loc_180002A34
0x180002a14  lea     rdx, __xc_z; Last
0x180002a1b  lea     rcx, __xc_a; First
0x180002a22  call    _initterm_0
0x180002a27  mov     cs:__scrt_current_native_startup_state, 2
0x180002a31  xor     dil, dil
0x180002a34  mov     cl, bl
0x180002a36  call    __scrt_release_startup_lock
0x180002a3b  test    dil, dil
0x180002a3e  jnz     short loc_180002A7A
0x180002a40  call    __scrt_get_dyn_tls_init_callback
0x180002a45  mov     rbx, rax
0x180002a48  cmp     qword ptr [rax], 0
0x180002a4c  jz      short loc_180002A6D
0x180002a4e  mov     rcx, rax
0x180002a51  call    __scrt_is_nonwritable_in_current_image
0x180002a56  test    al, al
0x180002a58  jz      short loc_180002A6D
0x180002a5a  mov     r8, rsi
0x180002a5d  mov     edx, 2
0x180002a62  mov     rcx, r14
0x180002a65  mov     rax, [rbx]
0x180002a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a6d  inc     cs:dword_18000A1D0
0x180002a73  mov     eax, 1
0x180002a78  jmp     short loc_180002A7C
0x180002a7a  xor     eax, eax
0x180002a7c  add     rsp, 28h
0x180002a80  pop     r14
0x180002a82  pop     rdi
0x180002a83  pop     rsi
0x180002a84  pop     rbx
0x180002a85  retn
0x180002a86  mov     ecx, 7
0x180002a8b  call    __scrt_fastfail
0x1800050ac  push    rbp
0x1800050ae  sub     rsp, 20h
0x1800050b2  mov     rbp, rdx
0x1800050b5  mov     cl, [rbp+60h]
0x1800050b8  add     rsp, 20h
0x1800050bc  pop     rbp
0x1800050bd  jmp     __scrt_release_startup_lock
```
