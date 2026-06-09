# dllmain_crt_process_attach

- ea: `0x180013e08`
- end: `0x180013f02`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180013db0`

## callees

- `0x180013e08`
- `0x180014198`
- `0x1800141d8`
- `0x180014214`
- `0x180014314`
- `0x1800143e8`
- `0x180014488`
- `0x180014a9c`
- `0x180014ac4`
- `0x180014ae8`
- `0x180014af8`
- `0x180014b04`
- `0x180014e86`
- `0x180014e92`
- `0x180025010`

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
  ++dword_18003DF10;
  return 1;
}

```

## disassembly

```asm
0x180013e08  push    rbx
0x180013e0a  push    rsi
0x180013e0b  push    rdi
0x180013e0c  push    r14
0x180013e0e  sub     rsp, 28h
0x180013e12  mov     rsi, rdx
0x180013e15  mov     r14, rcx
0x180013e18  xor     ecx, ecx
0x180013e1a  call    __scrt_initialize_crt
0x180013e1f  test    al, al
0x180013e21  jz      loc_180013EEA
0x180013e27  call    __scrt_acquire_startup_lock
0x180013e2c  mov     bl, al
0x180013e2e  mov     [rsp+48h+arg_10], al
0x180013e32  mov     dil, 1
0x180013e35  cmp     cs:__scrt_current_native_startup_state, 0
0x180013e3c  jnz     loc_180013EF6
0x180013e42  mov     cs:__scrt_current_native_startup_state, 1
0x180013e4c  call    __scrt_dllmain_before_initialize_c
0x180013e51  test    al, al
0x180013e53  jz      short loc_180013EA4
0x180013e55  call    _RTC_Initialize
0x180013e5a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180013e5f  call    __scrt_initialize_default_local_stdio_options
0x180013e64  lea     rdx, __xi_z; Last
0x180013e6b  lea     rcx, __xi_a; First
0x180013e72  call    _initterm_e_0
0x180013e77  test    eax, eax
0x180013e79  jnz     short loc_180013EA4
0x180013e7b  call    __scrt_dllmain_after_initialize_c
0x180013e80  test    al, al
0x180013e82  jz      short loc_180013EA4
0x180013e84  lea     rdx, __xc_z; Last
0x180013e8b  lea     rcx, __xc_a; First
0x180013e92  call    _initterm_0
0x180013e97  mov     cs:__scrt_current_native_startup_state, 2
0x180013ea1  xor     dil, dil
0x180013ea4  mov     cl, bl
0x180013ea6  call    __scrt_release_startup_lock
0x180013eab  test    dil, dil
0x180013eae  jnz     short loc_180013EEA
0x180013eb0  call    __scrt_get_dyn_tls_init_callback
0x180013eb5  mov     rbx, rax
0x180013eb8  cmp     qword ptr [rax], 0
0x180013ebc  jz      short loc_180013EDD
0x180013ebe  mov     rcx, rax
0x180013ec1  call    __scrt_is_nonwritable_in_current_image
0x180013ec6  test    al, al
0x180013ec8  jz      short loc_180013EDD
0x180013eca  mov     r8, rsi
0x180013ecd  mov     edx, 2
0x180013ed2  mov     rcx, r14
0x180013ed5  mov     rax, [rbx]
0x180013ed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013edd  inc     cs:dword_18003DF10
0x180013ee3  mov     eax, 1
0x180013ee8  jmp     short loc_180013EEC
0x180013eea  xor     eax, eax
0x180013eec  add     rsp, 28h
0x180013ef0  pop     r14
0x180013ef2  pop     rdi
0x180013ef3  pop     rsi
0x180013ef4  pop     rbx
0x180013ef5  retn
0x180013ef6  mov     ecx, 7
0x180013efb  call    __scrt_fastfail
0x180023a81  push    rbp
0x180023a83  sub     rsp, 20h
0x180023a87  mov     rbp, rdx
0x180023a8a  mov     cl, [rbp+60h]
0x180023a8d  add     rsp, 20h
0x180023a91  pop     rbp
0x180023a92  jmp     __scrt_release_startup_lock
```
