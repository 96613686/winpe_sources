# dllmain_crt_process_attach

- ea: `0x180001f58`
- end: `0x180002052`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001f00`

## callees

- `0x180001f58`
- `0x180002294`
- `0x1800022d4`
- `0x180002310`
- `0x180002410`
- `0x1800024e4`
- `0x180002584`
- `0x1800026fc`
- `0x180002724`
- `0x180002748`
- `0x180002758`
- `0x180002764`
- `0x180002ac6`
- `0x180002ad2`
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
  ++dword_18001E750;
  return 1;
}

```

## disassembly

```asm
0x180001f58  push    rbx
0x180001f5a  push    rsi
0x180001f5b  push    rdi
0x180001f5c  push    r14
0x180001f5e  sub     rsp, 28h
0x180001f62  mov     rsi, rdx
0x180001f65  mov     r14, rcx
0x180001f68  xor     ecx, ecx
0x180001f6a  call    __scrt_initialize_crt
0x180001f6f  test    al, al
0x180001f71  jz      loc_18000203A
0x180001f77  call    __scrt_acquire_startup_lock
0x180001f7c  mov     bl, al
0x180001f7e  mov     [rsp+48h+arg_10], al
0x180001f82  mov     dil, 1
0x180001f85  cmp     cs:__scrt_current_native_startup_state, 0
0x180001f8c  jnz     loc_180002046
0x180001f92  mov     cs:__scrt_current_native_startup_state, 1
0x180001f9c  call    __scrt_dllmain_before_initialize_c
0x180001fa1  test    al, al
0x180001fa3  jz      short loc_180001FF4
0x180001fa5  call    _RTC_Initialize
0x180001faa  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180001faf  call    __scrt_initialize_default_local_stdio_options
0x180001fb4  lea     rdx, __xi_z; Last
0x180001fbb  lea     rcx, __xi_a; First
0x180001fc2  call    _initterm_e_0
0x180001fc7  test    eax, eax
0x180001fc9  jnz     short loc_180001FF4
0x180001fcb  call    __scrt_dllmain_after_initialize_c
0x180001fd0  test    al, al
0x180001fd2  jz      short loc_180001FF4
0x180001fd4  lea     rdx, __xc_z; Last
0x180001fdb  lea     rcx, __xc_a; First
0x180001fe2  call    _initterm_0
0x180001fe7  mov     cs:__scrt_current_native_startup_state, 2
0x180001ff1  xor     dil, dil
0x180001ff4  mov     cl, bl
0x180001ff6  call    __scrt_release_startup_lock
0x180001ffb  test    dil, dil
0x180001ffe  jnz     short loc_18000203A
0x180002000  call    __scrt_get_dyn_tls_init_callback
0x180002005  mov     rbx, rax
0x180002008  cmp     qword ptr [rax], 0
0x18000200c  jz      short loc_18000202D
0x18000200e  mov     rcx, rax
0x180002011  call    __scrt_is_nonwritable_in_current_image
0x180002016  test    al, al
0x180002018  jz      short loc_18000202D
0x18000201a  mov     r8, rsi
0x18000201d  mov     edx, 2
0x180002022  mov     rcx, r14
0x180002025  mov     rax, [rbx]
0x180002028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000202d  inc     cs:dword_18001E750
0x180002033  mov     eax, 1
0x180002038  jmp     short loc_18000203C
0x18000203a  xor     eax, eax
0x18000203c  add     rsp, 28h
0x180002040  pop     r14
0x180002042  pop     rdi
0x180002043  pop     rsi
0x180002044  pop     rbx
0x180002045  retn
0x180002046  mov     ecx, 7
0x18000204b  call    __scrt_fastfail
0x1800140dc  push    rbp
0x1800140de  sub     rsp, 20h
0x1800140e2  mov     rbp, rdx
0x1800140e5  mov     cl, [rbp+60h]
0x1800140e8  add     rsp, 20h
0x1800140ec  pop     rbp
0x1800140ed  jmp     __scrt_release_startup_lock
```
