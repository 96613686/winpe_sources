# dllmain_crt_process_attach

- ea: `0x1800010f8`
- end: `0x1800011f2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800010a0`

## callees

- `0x1800010f8`
- `0x180001548`
- `0x180001570`
- `0x180001594`
- `0x1800015d4`
- `0x180001610`
- `0x180001710`
- `0x1800017e4`
- `0x180001884`
- `0x1800018e0`
- `0x1800018f0`
- `0x1800018fc`
- `0x180001c56`
- `0x180001c62`
- `0x18001e010`

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
  ++dword_1800274D0;
  return 1;
}

```

## disassembly

```asm
0x1800010f8  push    rbx
0x1800010fa  push    rsi
0x1800010fb  push    rdi
0x1800010fc  push    r14
0x1800010fe  sub     rsp, 28h
0x180001102  mov     rsi, rdx
0x180001105  mov     r14, rcx
0x180001108  xor     ecx, ecx
0x18000110a  call    __scrt_initialize_crt
0x18000110f  test    al, al
0x180001111  jz      loc_1800011DA
0x180001117  call    __scrt_acquire_startup_lock
0x18000111c  mov     bl, al
0x18000111e  mov     [rsp+48h+arg_10], al
0x180001122  mov     dil, 1
0x180001125  cmp     cs:__scrt_current_native_startup_state, 0
0x18000112c  jnz     loc_1800011E6
0x180001132  mov     cs:__scrt_current_native_startup_state, 1
0x18000113c  call    __scrt_dllmain_before_initialize_c
0x180001141  test    al, al
0x180001143  jz      short loc_180001194
0x180001145  call    _RTC_Initialize
0x18000114a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000114f  call    __scrt_initialize_default_local_stdio_options
0x180001154  lea     rdx, __xi_z; Last
0x18000115b  lea     rcx, __xi_a; First
0x180001162  call    _initterm_e_0
0x180001167  test    eax, eax
0x180001169  jnz     short loc_180001194
0x18000116b  call    __scrt_dllmain_after_initialize_c
0x180001170  test    al, al
0x180001172  jz      short loc_180001194
0x180001174  lea     rdx, __xc_z; Last
0x18000117b  lea     rcx, __xc_a; First
0x180001182  call    _initterm_0
0x180001187  mov     cs:__scrt_current_native_startup_state, 2
0x180001191  xor     dil, dil
0x180001194  mov     cl, bl
0x180001196  call    __scrt_release_startup_lock
0x18000119b  test    dil, dil
0x18000119e  jnz     short loc_1800011DA
0x1800011a0  call    __scrt_get_dyn_tls_init_callback
0x1800011a5  mov     rbx, rax
0x1800011a8  cmp     qword ptr [rax], 0
0x1800011ac  jz      short loc_1800011CD
0x1800011ae  mov     rcx, rax
0x1800011b1  call    __scrt_is_nonwritable_in_current_image
0x1800011b6  test    al, al
0x1800011b8  jz      short loc_1800011CD
0x1800011ba  mov     r8, rsi
0x1800011bd  mov     edx, 2
0x1800011c2  mov     rcx, r14
0x1800011c5  mov     rax, [rbx]
0x1800011c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800011cd  inc     cs:dword_1800274D0
0x1800011d3  mov     eax, 1
0x1800011d8  jmp     short loc_1800011DC
0x1800011da  xor     eax, eax
0x1800011dc  add     rsp, 28h
0x1800011e0  pop     r14
0x1800011e2  pop     rdi
0x1800011e3  pop     rsi
0x1800011e4  pop     rbx
0x1800011e5  retn
0x1800011e6  mov     ecx, 7
0x1800011eb  call    __scrt_fastfail
0x18001d40c  push    rbp
0x18001d40e  sub     rsp, 20h
0x18001d412  mov     rbp, rdx
0x18001d415  mov     cl, [rbp+60h]
0x18001d418  add     rsp, 20h
0x18001d41c  pop     rbp
0x18001d41d  jmp     __scrt_release_startup_lock
```
