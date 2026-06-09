# dllmain_crt_process_attach

- ea: `0x180002e98`
- end: `0x180002f92`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180002e40`

## callees

- `0x180002e98`
- `0x1800032dc`
- `0x18000331c`
- `0x180003358`
- `0x180003458`
- `0x18000352c`
- `0x1800035cc`
- `0x180003ad8`
- `0x180003b00`
- `0x180003b24`
- `0x180003b34`
- `0x180003b40`
- `0x180003c66`
- `0x180003c72`
- `0x180024010`

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
  ++dword_180032990;
  return 1;
}

```

## disassembly

```asm
0x180002e98  push    rbx
0x180002e9a  push    rsi
0x180002e9b  push    rdi
0x180002e9c  push    r14
0x180002e9e  sub     rsp, 28h
0x180002ea2  mov     rsi, rdx
0x180002ea5  mov     r14, rcx
0x180002ea8  xor     ecx, ecx
0x180002eaa  call    __scrt_initialize_crt
0x180002eaf  test    al, al
0x180002eb1  jz      loc_180002F7A
0x180002eb7  call    __scrt_acquire_startup_lock
0x180002ebc  mov     bl, al
0x180002ebe  mov     [rsp+48h+arg_10], al
0x180002ec2  mov     dil, 1
0x180002ec5  cmp     cs:__scrt_current_native_startup_state, 0
0x180002ecc  jnz     loc_180002F86
0x180002ed2  mov     cs:__scrt_current_native_startup_state, 1
0x180002edc  call    __scrt_dllmain_before_initialize_c
0x180002ee1  test    al, al
0x180002ee3  jz      short loc_180002F34
0x180002ee5  call    _RTC_Initialize
0x180002eea  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180002eef  call    __scrt_initialize_default_local_stdio_options
0x180002ef4  lea     rdx, __xi_z; Last
0x180002efb  lea     rcx, __xi_a; First
0x180002f02  call    _initterm_e_0
0x180002f07  test    eax, eax
0x180002f09  jnz     short loc_180002F34
0x180002f0b  call    __scrt_dllmain_after_initialize_c
0x180002f10  test    al, al
0x180002f12  jz      short loc_180002F34
0x180002f14  lea     rdx, __xc_z; Last
0x180002f1b  lea     rcx, __xc_a; First
0x180002f22  call    _initterm_0
0x180002f27  mov     cs:__scrt_current_native_startup_state, 2
0x180002f31  xor     dil, dil
0x180002f34  mov     cl, bl
0x180002f36  call    __scrt_release_startup_lock
0x180002f3b  test    dil, dil
0x180002f3e  jnz     short loc_180002F7A
0x180002f40  call    __scrt_get_dyn_tls_init_callback
0x180002f45  mov     rbx, rax
0x180002f48  cmp     qword ptr [rax], 0
0x180002f4c  jz      short loc_180002F6D
0x180002f4e  mov     rcx, rax
0x180002f51  call    __scrt_is_nonwritable_in_current_image
0x180002f56  test    al, al
0x180002f58  jz      short loc_180002F6D
0x180002f5a  mov     r8, rsi
0x180002f5d  mov     edx, 2
0x180002f62  mov     rcx, r14
0x180002f65  mov     rax, [rbx]
0x180002f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f6d  inc     cs:dword_180032990
0x180002f73  mov     eax, 1
0x180002f78  jmp     short loc_180002F7C
0x180002f7a  xor     eax, eax
0x180002f7c  add     rsp, 28h
0x180002f80  pop     r14
0x180002f82  pop     rdi
0x180002f83  pop     rsi
0x180002f84  pop     rbx
0x180002f85  retn
0x180002f86  mov     ecx, 7
0x180002f8b  call    __scrt_fastfail
0x180022a5c  push    rbp
0x180022a5e  sub     rsp, 20h
0x180022a62  mov     rbp, rdx
0x180022a65  mov     cl, [rbp+60h]
0x180022a68  add     rsp, 20h
0x180022a6c  pop     rbp
0x180022a6d  jmp     __scrt_release_startup_lock
```
