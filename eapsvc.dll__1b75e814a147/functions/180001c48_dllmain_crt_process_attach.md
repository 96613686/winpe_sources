# dllmain_crt_process_attach

- ea: `0x180001c48`
- end: `0x180001d42`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001bf0`

## callees

- `0x180001c48`
- `0x180001f84`
- `0x180001fc4`
- `0x180002000`
- `0x180002100`
- `0x1800021d4`
- `0x180002274`
- `0x18000236c`
- `0x180002450`
- `0x180002474`
- `0x180002484`
- `0x180002490`
- `0x1800027d6`
- `0x1800027e2`
- `0x180017010`

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
  ++dword_180020810;
  return 1;
}

```

## disassembly

```asm
0x180001c48  push    rbx
0x180001c4a  push    rsi
0x180001c4b  push    rdi
0x180001c4c  push    r14
0x180001c4e  sub     rsp, 28h
0x180001c52  mov     rsi, rdx
0x180001c55  mov     r14, rcx
0x180001c58  xor     ecx, ecx
0x180001c5a  call    __scrt_initialize_crt
0x180001c5f  test    al, al
0x180001c61  jz      loc_180001D2A
0x180001c67  call    __scrt_acquire_startup_lock
0x180001c6c  mov     bl, al
0x180001c6e  mov     [rsp+48h+arg_10], al
0x180001c72  mov     dil, 1
0x180001c75  cmp     cs:__scrt_current_native_startup_state, 0
0x180001c7c  jnz     loc_180001D36
0x180001c82  mov     cs:__scrt_current_native_startup_state, 1
0x180001c8c  call    __scrt_dllmain_before_initialize_c
0x180001c91  test    al, al
0x180001c93  jz      short loc_180001CE4
0x180001c95  call    _RTC_Initialize
0x180001c9a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180001c9f  call    __scrt_initialize_default_local_stdio_options
0x180001ca4  lea     rdx, __xi_z; Last
0x180001cab  lea     rcx, __xi_a; First
0x180001cb2  call    _initterm_e_0
0x180001cb7  test    eax, eax
0x180001cb9  jnz     short loc_180001CE4
0x180001cbb  call    __scrt_dllmain_after_initialize_c
0x180001cc0  test    al, al
0x180001cc2  jz      short loc_180001CE4
0x180001cc4  lea     rdx, __xc_z; Last
0x180001ccb  lea     rcx, __xc_a; First
0x180001cd2  call    _initterm_0
0x180001cd7  mov     cs:__scrt_current_native_startup_state, 2
0x180001ce1  xor     dil, dil
0x180001ce4  mov     cl, bl
0x180001ce6  call    __scrt_release_startup_lock
0x180001ceb  test    dil, dil
0x180001cee  jnz     short loc_180001D2A
0x180001cf0  call    __scrt_get_dyn_tls_init_callback
0x180001cf5  mov     rbx, rax
0x180001cf8  cmp     qword ptr [rax], 0
0x180001cfc  jz      short loc_180001D1D
0x180001cfe  mov     rcx, rax
0x180001d01  call    __scrt_is_nonwritable_in_current_image
0x180001d06  test    al, al
0x180001d08  jz      short loc_180001D1D
0x180001d0a  mov     r8, rsi
0x180001d0d  mov     edx, 2
0x180001d12  mov     rcx, r14
0x180001d15  mov     rax, [rbx]
0x180001d18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001d1d  inc     cs:dword_180020810
0x180001d23  mov     eax, 1
0x180001d28  jmp     short loc_180001D2C
0x180001d2a  xor     eax, eax
0x180001d2c  add     rsp, 28h
0x180001d30  pop     r14
0x180001d32  pop     rdi
0x180001d33  pop     rsi
0x180001d34  pop     rbx
0x180001d35  retn
0x180001d36  mov     ecx, 7
0x180001d3b  call    __scrt_fastfail
0x180014f0c  push    rbp
0x180014f0e  sub     rsp, 20h
0x180014f12  mov     rbp, rdx
0x180014f15  mov     cl, [rbp+60h]
0x180014f18  add     rsp, 20h
0x180014f1c  pop     rbp
0x180014f1d  jmp     __scrt_release_startup_lock
```
