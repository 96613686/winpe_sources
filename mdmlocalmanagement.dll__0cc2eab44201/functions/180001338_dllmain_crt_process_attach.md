# dllmain_crt_process_attach

- ea: `0x180001338`
- end: `0x180001432`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800012e0`

## callees

- `0x180001338`
- `0x180001684`
- `0x1800016c4`
- `0x180001700`
- `0x180001800`
- `0x1800018d4`
- `0x180001974`
- `0x180001b3c`
- `0x180001b64`
- `0x180001b88`
- `0x180001b98`
- `0x180001ba4`
- `0x180001f06`
- `0x180001f12`
- `0x180007010`

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
  ++dword_18000B290;
  return 1;
}

```

## disassembly

```asm
0x180001338  push    rbx
0x18000133a  push    rsi
0x18000133b  push    rdi
0x18000133c  push    r14
0x18000133e  sub     rsp, 28h
0x180001342  mov     rsi, rdx
0x180001345  mov     r14, rcx
0x180001348  xor     ecx, ecx
0x18000134a  call    __scrt_initialize_crt
0x18000134f  test    al, al
0x180001351  jz      loc_18000141A
0x180001357  call    __scrt_acquire_startup_lock
0x18000135c  mov     bl, al
0x18000135e  mov     [rsp+48h+arg_10], al
0x180001362  mov     dil, 1
0x180001365  cmp     cs:__scrt_current_native_startup_state, 0
0x18000136c  jnz     loc_180001426
0x180001372  mov     cs:__scrt_current_native_startup_state, 1
0x18000137c  call    __scrt_dllmain_before_initialize_c
0x180001381  test    al, al
0x180001383  jz      short loc_1800013D4
0x180001385  call    _RTC_Initialize
0x18000138a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000138f  call    __scrt_initialize_default_local_stdio_options
0x180001394  lea     rdx, __xi_z; Last
0x18000139b  lea     rcx, __xi_a; First
0x1800013a2  call    _initterm_e_0
0x1800013a7  test    eax, eax
0x1800013a9  jnz     short loc_1800013D4
0x1800013ab  call    __scrt_dllmain_after_initialize_c
0x1800013b0  test    al, al
0x1800013b2  jz      short loc_1800013D4
0x1800013b4  lea     rdx, __xc_z; Last
0x1800013bb  lea     rcx, __xc_a; First
0x1800013c2  call    _initterm_0
0x1800013c7  mov     cs:__scrt_current_native_startup_state, 2
0x1800013d1  xor     dil, dil
0x1800013d4  mov     cl, bl
0x1800013d6  call    __scrt_release_startup_lock
0x1800013db  test    dil, dil
0x1800013de  jnz     short loc_18000141A
0x1800013e0  call    __scrt_get_dyn_tls_init_callback
0x1800013e5  mov     rbx, rax
0x1800013e8  cmp     qword ptr [rax], 0
0x1800013ec  jz      short loc_18000140D
0x1800013ee  mov     rcx, rax
0x1800013f1  call    __scrt_is_nonwritable_in_current_image
0x1800013f6  test    al, al
0x1800013f8  jz      short loc_18000140D
0x1800013fa  mov     r8, rsi
0x1800013fd  mov     edx, 2
0x180001402  mov     rcx, r14
0x180001405  mov     rax, [rbx]
0x180001408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000140d  inc     cs:dword_18000B290
0x180001413  mov     eax, 1
0x180001418  jmp     short loc_18000141C
0x18000141a  xor     eax, eax
0x18000141c  add     rsp, 28h
0x180001420  pop     r14
0x180001422  pop     rdi
0x180001423  pop     rsi
0x180001424  pop     rbx
0x180001425  retn
0x180001426  mov     ecx, 7
0x18000142b  call    __scrt_fastfail
0x180006b7c  push    rbp
0x180006b7e  sub     rsp, 20h
0x180006b82  mov     rbp, rdx
0x180006b85  mov     cl, [rbp+60h]
0x180006b88  add     rsp, 20h
0x180006b8c  pop     rbp
0x180006b8d  jmp     __scrt_release_startup_lock
```
