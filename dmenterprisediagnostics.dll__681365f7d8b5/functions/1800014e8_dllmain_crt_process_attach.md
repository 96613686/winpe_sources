# dllmain_crt_process_attach

- ea: `0x1800014e8`
- end: `0x1800015e2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001490`

## callees

- `0x1800014e8`
- `0x180001950`
- `0x180001990`
- `0x1800019cc`
- `0x180001acc`
- `0x180001ba0`
- `0x180001c40`
- `0x180001e08`
- `0x180001e30`
- `0x180001e54`
- `0x180001e64`
- `0x180001e70`
- `0x180002276`
- `0x180002282`
- `0x180027010`

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
  ++dword_180034D10;
  return 1;
}

```

## disassembly

```asm
0x1800014e8  push    rbx
0x1800014ea  push    rsi
0x1800014eb  push    rdi
0x1800014ec  push    r14
0x1800014ee  sub     rsp, 28h
0x1800014f2  mov     rsi, rdx
0x1800014f5  mov     r14, rcx
0x1800014f8  xor     ecx, ecx
0x1800014fa  call    __scrt_initialize_crt
0x1800014ff  test    al, al
0x180001501  jz      loc_1800015CA
0x180001507  call    __scrt_acquire_startup_lock
0x18000150c  mov     bl, al
0x18000150e  mov     [rsp+48h+arg_10], al
0x180001512  mov     dil, 1
0x180001515  cmp     cs:__scrt_current_native_startup_state, 0
0x18000151c  jnz     loc_1800015D6
0x180001522  mov     cs:__scrt_current_native_startup_state, 1
0x18000152c  call    __scrt_dllmain_before_initialize_c
0x180001531  test    al, al
0x180001533  jz      short loc_180001584
0x180001535  call    _RTC_Initialize
0x18000153a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000153f  call    __scrt_initialize_default_local_stdio_options
0x180001544  lea     rdx, __xi_z; Last
0x18000154b  lea     rcx, __xi_a; First
0x180001552  call    _initterm_e_0
0x180001557  test    eax, eax
0x180001559  jnz     short loc_180001584
0x18000155b  call    __scrt_dllmain_after_initialize_c
0x180001560  test    al, al
0x180001562  jz      short loc_180001584
0x180001564  lea     rdx, __xc_z; Last
0x18000156b  lea     rcx, __xc_a; First
0x180001572  call    _initterm_0
0x180001577  mov     cs:__scrt_current_native_startup_state, 2
0x180001581  xor     dil, dil
0x180001584  mov     cl, bl
0x180001586  call    __scrt_release_startup_lock
0x18000158b  test    dil, dil
0x18000158e  jnz     short loc_1800015CA
0x180001590  call    __scrt_get_dyn_tls_init_callback
0x180001595  mov     rbx, rax
0x180001598  cmp     qword ptr [rax], 0
0x18000159c  jz      short loc_1800015BD
0x18000159e  mov     rcx, rax
0x1800015a1  call    __scrt_is_nonwritable_in_current_image
0x1800015a6  test    al, al
0x1800015a8  jz      short loc_1800015BD
0x1800015aa  mov     r8, rsi
0x1800015ad  mov     edx, 2
0x1800015b2  mov     rcx, r14
0x1800015b5  mov     rax, [rbx]
0x1800015b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800015bd  inc     cs:dword_180034D10
0x1800015c3  mov     eax, 1
0x1800015c8  jmp     short loc_1800015CC
0x1800015ca  xor     eax, eax
0x1800015cc  add     rsp, 28h
0x1800015d0  pop     r14
0x1800015d2  pop     rdi
0x1800015d3  pop     rsi
0x1800015d4  pop     rbx
0x1800015d5  retn
0x1800015d6  mov     ecx, 7
0x1800015db  call    __scrt_fastfail
0x18002531c  push    rbp
0x18002531e  sub     rsp, 20h
0x180025322  mov     rbp, rdx
0x180025325  mov     cl, [rbp+60h]
0x180025328  add     rsp, 20h
0x18002532c  pop     rbp
0x18002532d  jmp     __scrt_release_startup_lock
```
