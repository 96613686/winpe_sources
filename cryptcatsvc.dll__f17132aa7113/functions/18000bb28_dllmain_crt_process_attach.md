# dllmain_crt_process_attach

- ea: `0x18000bb28`
- end: `0x18000bc22`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x18000bad0`

## callees

- `0x18000bb28`
- `0x18000be64`
- `0x18000bea4`
- `0x18000bee0`
- `0x18000bfe0`
- `0x18000c0b4`
- `0x18000c154`
- `0x18000c5d8`
- `0x18000c600`
- `0x18000c624`
- `0x18000c634`
- `0x18000c640`
- `0x18000c6e6`
- `0x18000c6f2`
- `0x180022010`

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
  ++dword_180031370;
  return 1;
}

```

## disassembly

```asm
0x18000bb28  push    rbx
0x18000bb2a  push    rsi
0x18000bb2b  push    rdi
0x18000bb2c  push    r14
0x18000bb2e  sub     rsp, 28h
0x18000bb32  mov     rsi, rdx
0x18000bb35  mov     r14, rcx
0x18000bb38  xor     ecx, ecx
0x18000bb3a  call    __scrt_initialize_crt
0x18000bb3f  test    al, al
0x18000bb41  jz      loc_18000BC0A
0x18000bb47  call    __scrt_acquire_startup_lock
0x18000bb4c  mov     bl, al
0x18000bb4e  mov     [rsp+48h+arg_10], al
0x18000bb52  mov     dil, 1
0x18000bb55  cmp     cs:__scrt_current_native_startup_state, 0
0x18000bb5c  jnz     loc_18000BC16
0x18000bb62  mov     cs:__scrt_current_native_startup_state, 1
0x18000bb6c  call    __scrt_dllmain_before_initialize_c
0x18000bb71  test    al, al
0x18000bb73  jz      short loc_18000BBC4
0x18000bb75  call    _RTC_Initialize
0x18000bb7a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000bb7f  call    __scrt_initialize_default_local_stdio_options
0x18000bb84  lea     rdx, __xi_z; Last
0x18000bb8b  lea     rcx, __xi_a; First
0x18000bb92  call    _initterm_e_0
0x18000bb97  test    eax, eax
0x18000bb99  jnz     short loc_18000BBC4
0x18000bb9b  call    __scrt_dllmain_after_initialize_c
0x18000bba0  test    al, al
0x18000bba2  jz      short loc_18000BBC4
0x18000bba4  lea     rdx, __xc_z; Last
0x18000bbab  lea     rcx, __xc_a; First
0x18000bbb2  call    _initterm_0
0x18000bbb7  mov     cs:__scrt_current_native_startup_state, 2
0x18000bbc1  xor     dil, dil
0x18000bbc4  mov     cl, bl
0x18000bbc6  call    __scrt_release_startup_lock
0x18000bbcb  test    dil, dil
0x18000bbce  jnz     short loc_18000BC0A
0x18000bbd0  call    __scrt_get_dyn_tls_init_callback
0x18000bbd5  mov     rbx, rax
0x18000bbd8  cmp     qword ptr [rax], 0
0x18000bbdc  jz      short loc_18000BBFD
0x18000bbde  mov     rcx, rax
0x18000bbe1  call    __scrt_is_nonwritable_in_current_image
0x18000bbe6  test    al, al
0x18000bbe8  jz      short loc_18000BBFD
0x18000bbea  mov     r8, rsi
0x18000bbed  mov     edx, 2
0x18000bbf2  mov     rcx, r14
0x18000bbf5  mov     rax, [rbx]
0x18000bbf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbfd  inc     cs:dword_180031370
0x18000bc03  mov     eax, 1
0x18000bc08  jmp     short loc_18000BC0C
0x18000bc0a  xor     eax, eax
0x18000bc0c  add     rsp, 28h
0x18000bc10  pop     r14
0x18000bc12  pop     rdi
0x18000bc13  pop     rsi
0x18000bc14  pop     rbx
0x18000bc15  retn
0x18000bc16  mov     ecx, 7
0x18000bc1b  call    __scrt_fastfail
0x180021680  push    rbp
0x180021682  sub     rsp, 20h
0x180021686  mov     rbp, rdx
0x180021689  mov     cl, [rbp+60h]
0x18002168c  add     rsp, 20h
0x180021690  pop     rbp
0x180021691  jmp     __scrt_release_startup_lock
```
