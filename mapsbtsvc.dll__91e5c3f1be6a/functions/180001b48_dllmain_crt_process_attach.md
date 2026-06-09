# dllmain_crt_process_attach

- ea: `0x180001b48`
- end: `0x180001c42`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001af0`

## callees

- `0x180001b48`
- `0x180001ea0`
- `0x180001ee0`
- `0x180001f1c`
- `0x18000201c`
- `0x1800020f0`
- `0x180002190`
- `0x18000234c`
- `0x180002374`
- `0x180002398`
- `0x1800023a8`
- `0x1800023b4`
- `0x1800027c6`
- `0x1800027d2`
- `0x180015010`

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
  ++dword_18001D590;
  return 1;
}

```

## disassembly

```asm
0x180001b48  push    rbx
0x180001b4a  push    rsi
0x180001b4b  push    rdi
0x180001b4c  push    r14
0x180001b4e  sub     rsp, 28h
0x180001b52  mov     rsi, rdx
0x180001b55  mov     r14, rcx
0x180001b58  xor     ecx, ecx
0x180001b5a  call    __scrt_initialize_crt
0x180001b5f  test    al, al
0x180001b61  jz      loc_180001C2A
0x180001b67  call    __scrt_acquire_startup_lock
0x180001b6c  mov     bl, al
0x180001b6e  mov     [rsp+48h+arg_10], al
0x180001b72  mov     dil, 1
0x180001b75  cmp     cs:__scrt_current_native_startup_state, 0
0x180001b7c  jnz     loc_180001C36
0x180001b82  mov     cs:__scrt_current_native_startup_state, 1
0x180001b8c  call    __scrt_dllmain_before_initialize_c
0x180001b91  test    al, al
0x180001b93  jz      short loc_180001BE4
0x180001b95  call    _RTC_Initialize
0x180001b9a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180001b9f  call    __scrt_initialize_default_local_stdio_options
0x180001ba4  lea     rdx, __xi_z; Last
0x180001bab  lea     rcx, __xi_a; First
0x180001bb2  call    _initterm_e_0
0x180001bb7  test    eax, eax
0x180001bb9  jnz     short loc_180001BE4
0x180001bbb  call    __scrt_dllmain_after_initialize_c
0x180001bc0  test    al, al
0x180001bc2  jz      short loc_180001BE4
0x180001bc4  lea     rdx, __xc_z; Last
0x180001bcb  lea     rcx, __xc_a; First
0x180001bd2  call    _initterm_0
0x180001bd7  mov     cs:__scrt_current_native_startup_state, 2
0x180001be1  xor     dil, dil
0x180001be4  mov     cl, bl
0x180001be6  call    __scrt_release_startup_lock
0x180001beb  test    dil, dil
0x180001bee  jnz     short loc_180001C2A
0x180001bf0  call    __scrt_get_dyn_tls_init_callback
0x180001bf5  mov     rbx, rax
0x180001bf8  cmp     qword ptr [rax], 0
0x180001bfc  jz      short loc_180001C1D
0x180001bfe  mov     rcx, rax
0x180001c01  call    __scrt_is_nonwritable_in_current_image
0x180001c06  test    al, al
0x180001c08  jz      short loc_180001C1D
0x180001c0a  mov     r8, rsi
0x180001c0d  mov     edx, 2
0x180001c12  mov     rcx, r14
0x180001c15  mov     rax, [rbx]
0x180001c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c1d  inc     cs:dword_18001D590
0x180001c23  mov     eax, 1
0x180001c28  jmp     short loc_180001C2C
0x180001c2a  xor     eax, eax
0x180001c2c  add     rsp, 28h
0x180001c30  pop     r14
0x180001c32  pop     rdi
0x180001c33  pop     rsi
0x180001c34  pop     rbx
0x180001c35  retn
0x180001c36  mov     ecx, 7
0x180001c3b  call    __scrt_fastfail
0x180013a6c  push    rbp
0x180013a6e  sub     rsp, 20h
0x180013a72  mov     rbp, rdx
0x180013a75  mov     cl, [rbp+60h]
0x180013a78  add     rsp, 20h
0x180013a7c  pop     rbp
0x180013a7d  jmp     __scrt_release_startup_lock
```
