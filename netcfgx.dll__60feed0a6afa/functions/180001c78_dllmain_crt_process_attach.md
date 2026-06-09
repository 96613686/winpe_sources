# dllmain_crt_process_attach

- ea: `0x180001c78`
- end: `0x180001d72`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001c20`

## callees

- `0x180001c78`
- `0x180002020`
- `0x180002060`
- `0x18000209c`
- `0x18000219c`
- `0x180002270`
- `0x180002310`
- `0x18000259c`
- `0x1800025c4`
- `0x1800025e8`
- `0x1800025f8`
- `0x180002604`
- `0x180002936`
- `0x180002942`
- `0x180013010`

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
  ++dword_18001A4D0;
  return 1;
}

```

## disassembly

```asm
0x180001c78  push    rbx
0x180001c7a  push    rsi
0x180001c7b  push    rdi
0x180001c7c  push    r14
0x180001c7e  sub     rsp, 28h
0x180001c82  mov     rsi, rdx
0x180001c85  mov     r14, rcx
0x180001c88  xor     ecx, ecx
0x180001c8a  call    __scrt_initialize_crt
0x180001c8f  test    al, al
0x180001c91  jz      loc_180001D5A
0x180001c97  call    __scrt_acquire_startup_lock
0x180001c9c  mov     bl, al
0x180001c9e  mov     [rsp+48h+arg_10], al
0x180001ca2  mov     dil, 1
0x180001ca5  cmp     cs:__scrt_current_native_startup_state, 0
0x180001cac  jnz     loc_180001D66
0x180001cb2  mov     cs:__scrt_current_native_startup_state, 1
0x180001cbc  call    __scrt_dllmain_before_initialize_c
0x180001cc1  test    al, al
0x180001cc3  jz      short loc_180001D14
0x180001cc5  call    _RTC_Initialize
0x180001cca  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180001ccf  call    __scrt_initialize_default_local_stdio_options
0x180001cd4  lea     rdx, __xi_z; Last
0x180001cdb  lea     rcx, __xi_a; First
0x180001ce2  call    _initterm_e_0
0x180001ce7  test    eax, eax
0x180001ce9  jnz     short loc_180001D14
0x180001ceb  call    __scrt_dllmain_after_initialize_c
0x180001cf0  test    al, al
0x180001cf2  jz      short loc_180001D14
0x180001cf4  lea     rdx, __xc_z; Last
0x180001cfb  lea     rcx, __xc_a; First
0x180001d02  call    _initterm_0
0x180001d07  mov     cs:__scrt_current_native_startup_state, 2
0x180001d11  xor     dil, dil
0x180001d14  mov     cl, bl
0x180001d16  call    __scrt_release_startup_lock
0x180001d1b  test    dil, dil
0x180001d1e  jnz     short loc_180001D5A
0x180001d20  call    __scrt_get_dyn_tls_init_callback
0x180001d25  mov     rbx, rax
0x180001d28  cmp     qword ptr [rax], 0
0x180001d2c  jz      short loc_180001D4D
0x180001d2e  mov     rcx, rax
0x180001d31  call    __scrt_is_nonwritable_in_current_image
0x180001d36  test    al, al
0x180001d38  jz      short loc_180001D4D
0x180001d3a  mov     r8, rsi
0x180001d3d  mov     edx, 2
0x180001d42  mov     rcx, r14
0x180001d45  mov     rax, [rbx]
0x180001d48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d4d  inc     cs:dword_18001A4D0
0x180001d53  mov     eax, 1
0x180001d58  jmp     short loc_180001D5C
0x180001d5a  xor     eax, eax
0x180001d5c  add     rsp, 28h
0x180001d60  pop     r14
0x180001d62  pop     rdi
0x180001d63  pop     rsi
0x180001d64  pop     rbx
0x180001d65  retn
0x180001d66  mov     ecx, 7
0x180001d6b  call    __scrt_fastfail
0x18001244c  push    rbp
0x18001244e  sub     rsp, 20h
0x180012452  mov     rbp, rdx
0x180012455  mov     cl, [rbp+60h]
0x180012458  add     rsp, 20h
0x18001245c  pop     rbp
0x18001245d  jmp     __scrt_release_startup_lock
```
