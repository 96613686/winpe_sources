# dllmain_crt_process_attach

- ea: `0x180002b38`
- end: `0x180002c32`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180002ae0`

## callees

- `0x180002b38`
- `0x180002edc`
- `0x180002f1c`
- `0x180002f58`
- `0x180003058`
- `0x18000312c`
- `0x1800031cc`
- `0x1800036b0`
- `0x1800036d8`
- `0x1800036fc`
- `0x18000370c`
- `0x180003718`
- `0x180003806`
- `0x180003812`
- `0x180023010`

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
  ++dword_18002F530;
  return 1;
}

```

## disassembly

```asm
0x180002b38  push    rbx
0x180002b3a  push    rsi
0x180002b3b  push    rdi
0x180002b3c  push    r14
0x180002b3e  sub     rsp, 28h
0x180002b42  mov     rsi, rdx
0x180002b45  mov     r14, rcx
0x180002b48  xor     ecx, ecx
0x180002b4a  call    __scrt_initialize_crt
0x180002b4f  test    al, al
0x180002b51  jz      loc_180002C1A
0x180002b57  call    __scrt_acquire_startup_lock
0x180002b5c  mov     bl, al
0x180002b5e  mov     [rsp+48h+arg_10], al
0x180002b62  mov     dil, 1
0x180002b65  cmp     cs:__scrt_current_native_startup_state, 0
0x180002b6c  jnz     loc_180002C26
0x180002b72  mov     cs:__scrt_current_native_startup_state, 1
0x180002b7c  call    __scrt_dllmain_before_initialize_c
0x180002b81  test    al, al
0x180002b83  jz      short loc_180002BD4
0x180002b85  call    _RTC_Initialize
0x180002b8a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180002b8f  call    __scrt_initialize_default_local_stdio_options
0x180002b94  lea     rdx, __xi_z; Last
0x180002b9b  lea     rcx, __xi_a; First
0x180002ba2  call    _initterm_e_0
0x180002ba7  test    eax, eax
0x180002ba9  jnz     short loc_180002BD4
0x180002bab  call    __scrt_dllmain_after_initialize_c
0x180002bb0  test    al, al
0x180002bb2  jz      short loc_180002BD4
0x180002bb4  lea     rdx, __xc_z; Last
0x180002bbb  lea     rcx, __xc_a; First
0x180002bc2  call    _initterm_0
0x180002bc7  mov     cs:__scrt_current_native_startup_state, 2
0x180002bd1  xor     dil, dil
0x180002bd4  mov     cl, bl
0x180002bd6  call    __scrt_release_startup_lock
0x180002bdb  test    dil, dil
0x180002bde  jnz     short loc_180002C1A
0x180002be0  call    __scrt_get_dyn_tls_init_callback
0x180002be5  mov     rbx, rax
0x180002be8  cmp     qword ptr [rax], 0
0x180002bec  jz      short loc_180002C0D
0x180002bee  mov     rcx, rax
0x180002bf1  call    __scrt_is_nonwritable_in_current_image
0x180002bf6  test    al, al
0x180002bf8  jz      short loc_180002C0D
0x180002bfa  mov     r8, rsi
0x180002bfd  mov     edx, 2
0x180002c02  mov     rcx, r14
0x180002c05  mov     rax, [rbx]
0x180002c08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c0d  inc     cs:dword_18002F530
0x180002c13  mov     eax, 1
0x180002c18  jmp     short loc_180002C1C
0x180002c1a  xor     eax, eax
0x180002c1c  add     rsp, 28h
0x180002c20  pop     r14
0x180002c22  pop     rdi
0x180002c23  pop     rsi
0x180002c24  pop     rbx
0x180002c25  retn
0x180002c26  mov     ecx, 7
0x180002c2b  call    __scrt_fastfail
0x1800208fc  push    rbp
0x1800208fe  sub     rsp, 20h
0x180020902  mov     rbp, rdx
0x180020905  mov     cl, [rbp+60h]
0x180020908  add     rsp, 20h
0x18002090c  pop     rbp
0x18002090d  jmp     __scrt_release_startup_lock
```
