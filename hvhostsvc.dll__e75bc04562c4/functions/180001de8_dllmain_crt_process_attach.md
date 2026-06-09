# dllmain_crt_process_attach

- ea: `0x180001de8`
- end: `0x180001ee2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001d90`

## callees

- `0x180001de8`
- `0x180002124`
- `0x180002164`
- `0x1800021a0`
- `0x1800022a0`
- `0x180002374`
- `0x180002414`
- `0x1800025f4`
- `0x18000261c`
- `0x180002640`
- `0x180002650`
- `0x18000265c`
- `0x1800029c6`
- `0x1800029d2`
- `0x18000a010`

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
  ++dword_1800125B0;
  return 1;
}

```

## disassembly

```asm
0x180001de8  push    rbx
0x180001dea  push    rsi
0x180001deb  push    rdi
0x180001dec  push    r14
0x180001dee  sub     rsp, 28h
0x180001df2  mov     rsi, rdx
0x180001df5  mov     r14, rcx
0x180001df8  xor     ecx, ecx
0x180001dfa  call    __scrt_initialize_crt
0x180001dff  test    al, al
0x180001e01  jz      loc_180001ECA
0x180001e07  call    __scrt_acquire_startup_lock
0x180001e0c  mov     bl, al
0x180001e0e  mov     [rsp+48h+arg_10], al
0x180001e12  mov     dil, 1
0x180001e15  cmp     cs:__scrt_current_native_startup_state, 0
0x180001e1c  jnz     loc_180001ED6
0x180001e22  mov     cs:__scrt_current_native_startup_state, 1
0x180001e2c  call    __scrt_dllmain_before_initialize_c
0x180001e31  test    al, al
0x180001e33  jz      short loc_180001E84
0x180001e35  call    _RTC_Initialize
0x180001e3a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180001e3f  call    __scrt_initialize_default_local_stdio_options
0x180001e44  lea     rdx, __xi_z; Last
0x180001e4b  lea     rcx, __xi_a; First
0x180001e52  call    _initterm_e_0
0x180001e57  test    eax, eax
0x180001e59  jnz     short loc_180001E84
0x180001e5b  call    __scrt_dllmain_after_initialize_c
0x180001e60  test    al, al
0x180001e62  jz      short loc_180001E84
0x180001e64  lea     rdx, __xc_z; Last
0x180001e6b  lea     rcx, __xc_a; First
0x180001e72  call    _initterm_0
0x180001e77  mov     cs:__scrt_current_native_startup_state, 2
0x180001e81  xor     dil, dil
0x180001e84  mov     cl, bl
0x180001e86  call    __scrt_release_startup_lock
0x180001e8b  test    dil, dil
0x180001e8e  jnz     short loc_180001ECA
0x180001e90  call    __scrt_get_dyn_tls_init_callback
0x180001e95  mov     rbx, rax
0x180001e98  cmp     qword ptr [rax], 0
0x180001e9c  jz      short loc_180001EBD
0x180001e9e  mov     rcx, rax
0x180001ea1  call    __scrt_is_nonwritable_in_current_image
0x180001ea6  test    al, al
0x180001ea8  jz      short loc_180001EBD
0x180001eaa  mov     r8, rsi
0x180001ead  mov     edx, 2
0x180001eb2  mov     rcx, r14
0x180001eb5  mov     rax, [rbx]
0x180001eb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001ebd  inc     cs:dword_1800125B0
0x180001ec3  mov     eax, 1
0x180001ec8  jmp     short loc_180001ECC
0x180001eca  xor     eax, eax
0x180001ecc  add     rsp, 28h
0x180001ed0  pop     r14
0x180001ed2  pop     rdi
0x180001ed3  pop     rsi
0x180001ed4  pop     rbx
0x180001ed5  retn
0x180001ed6  mov     ecx, 7
0x180001edb  call    __scrt_fastfail
0x180009144  push    rbp
0x180009146  sub     rsp, 20h
0x18000914a  mov     rbp, rdx
0x18000914d  mov     cl, [rbp+60h]
0x180009150  add     rsp, 20h
0x180009154  pop     rbp
0x180009155  jmp     __scrt_release_startup_lock
```
