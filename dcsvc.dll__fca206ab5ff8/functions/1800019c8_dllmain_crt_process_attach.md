# dllmain_crt_process_attach

- ea: `0x1800019c8`
- end: `0x180001ac2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001970`

## callees

- `0x1800019c8`
- `0x180001d4c`
- `0x180001d8c`
- `0x180001dc8`
- `0x180001ec8`
- `0x180001f9c`
- `0x18000203c`
- `0x1800021e0`
- `0x180002208`
- `0x18000222c`
- `0x18000223c`
- `0x180002248`
- `0x1800025a6`
- `0x1800025b2`
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
    _scrt_fastfail(7u);
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
  ++dword_18001B610;
  return 1;
}

```

## disassembly

```asm
0x1800019c8  push    rbx
0x1800019ca  push    rsi
0x1800019cb  push    rdi
0x1800019cc  push    r14
0x1800019ce  sub     rsp, 28h
0x1800019d2  mov     rsi, rdx
0x1800019d5  mov     r14, rcx
0x1800019d8  xor     ecx, ecx
0x1800019da  call    __scrt_initialize_crt
0x1800019df  test    al, al
0x1800019e1  jz      loc_180001AAA
0x1800019e7  call    __scrt_acquire_startup_lock
0x1800019ec  mov     bl, al
0x1800019ee  mov     [rsp+48h+arg_10], al
0x1800019f2  mov     dil, 1
0x1800019f5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800019fc  jnz     loc_180001AB6
0x180001a02  mov     cs:__scrt_current_native_startup_state, 1
0x180001a0c  call    __scrt_dllmain_before_initialize_c
0x180001a11  test    al, al
0x180001a13  jz      short loc_180001A64
0x180001a15  call    _RTC_Initialize
0x180001a1a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180001a1f  call    __scrt_initialize_default_local_stdio_options
0x180001a24  lea     rdx, __xi_z; Last
0x180001a2b  lea     rcx, __xi_a; First
0x180001a32  call    _initterm_e_0
0x180001a37  test    eax, eax
0x180001a39  jnz     short loc_180001A64
0x180001a3b  call    __scrt_dllmain_after_initialize_c
0x180001a40  test    al, al
0x180001a42  jz      short loc_180001A64
0x180001a44  lea     rdx, __xc_z; Last
0x180001a4b  lea     rcx, __xc_a; First
0x180001a52  call    _initterm_0
0x180001a57  mov     cs:__scrt_current_native_startup_state, 2
0x180001a61  xor     dil, dil
0x180001a64  mov     cl, bl
0x180001a66  call    __scrt_release_startup_lock
0x180001a6b  test    dil, dil
0x180001a6e  jnz     short loc_180001AAA
0x180001a70  call    __scrt_get_dyn_tls_init_callback
0x180001a75  mov     rbx, rax
0x180001a78  cmp     qword ptr [rax], 0
0x180001a7c  jz      short loc_180001A9D
0x180001a7e  mov     rcx, rax
0x180001a81  call    __scrt_is_nonwritable_in_current_image
0x180001a86  test    al, al
0x180001a88  jz      short loc_180001A9D
0x180001a8a  mov     r8, rsi
0x180001a8d  mov     edx, 2
0x180001a92  mov     rcx, r14
0x180001a95  mov     rax, [rbx]
0x180001a98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a9d  inc     cs:dword_18001B610
0x180001aa3  mov     eax, 1
0x180001aa8  jmp     short loc_180001AAC
0x180001aaa  xor     eax, eax
0x180001aac  add     rsp, 28h
0x180001ab0  pop     r14
0x180001ab2  pop     rdi
0x180001ab3  pop     rsi
0x180001ab4  pop     rbx
0x180001ab5  retn
0x180001ab6  mov     ecx, 7
0x180001abb  call    __scrt_fastfail
0x180011cec  push    rbp
0x180011cee  sub     rsp, 20h
0x180011cf2  mov     rbp, rdx
0x180011cf5  mov     cl, [rbp+60h]
0x180011cf8  add     rsp, 20h
0x180011cfc  pop     rbp
0x180011cfd  jmp     __scrt_release_startup_lock
```
