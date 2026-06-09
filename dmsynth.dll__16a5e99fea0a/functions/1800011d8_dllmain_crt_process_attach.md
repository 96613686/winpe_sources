# dllmain_crt_process_attach

- ea: `0x1800011d8`
- end: `0x1800012d2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001180`

## callees

- `0x1800011d8`
- `0x1800015fc`
- `0x180001624`
- `0x180001648`
- `0x180001688`
- `0x1800016c4`
- `0x1800017c4`
- `0x180001898`
- `0x180001938`
- `0x180001994`
- `0x1800019a4`
- `0x1800019b0`
- `0x180001ce6`
- `0x180001cf2`
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
  ++dword_18001E630;
  return 1;
}

```

## disassembly

```asm
0x1800011d8  push    rbx
0x1800011da  push    rsi
0x1800011db  push    rdi
0x1800011dc  push    r14
0x1800011de  sub     rsp, 28h
0x1800011e2  mov     rsi, rdx
0x1800011e5  mov     r14, rcx
0x1800011e8  xor     ecx, ecx
0x1800011ea  call    __scrt_initialize_crt
0x1800011ef  test    al, al
0x1800011f1  jz      loc_1800012BA
0x1800011f7  call    __scrt_acquire_startup_lock
0x1800011fc  mov     bl, al
0x1800011fe  mov     [rsp+48h+arg_10], al
0x180001202  mov     dil, 1
0x180001205  cmp     cs:__scrt_current_native_startup_state, 0
0x18000120c  jnz     loc_1800012C6
0x180001212  mov     cs:__scrt_current_native_startup_state, 1
0x18000121c  call    __scrt_dllmain_before_initialize_c
0x180001221  test    al, al
0x180001223  jz      short loc_180001274
0x180001225  call    _RTC_Initialize
0x18000122a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000122f  call    __scrt_initialize_default_local_stdio_options
0x180001234  lea     rdx, __xi_z; Last
0x18000123b  lea     rcx, __xi_a; First
0x180001242  call    _initterm_e_0
0x180001247  test    eax, eax
0x180001249  jnz     short loc_180001274
0x18000124b  call    __scrt_dllmain_after_initialize_c
0x180001250  test    al, al
0x180001252  jz      short loc_180001274
0x180001254  lea     rdx, __xc_z; Last
0x18000125b  lea     rcx, __xc_a; First
0x180001262  call    _initterm_0
0x180001267  mov     cs:__scrt_current_native_startup_state, 2
0x180001271  xor     dil, dil
0x180001274  mov     cl, bl
0x180001276  call    __scrt_release_startup_lock
0x18000127b  test    dil, dil
0x18000127e  jnz     short loc_1800012BA
0x180001280  call    __scrt_get_dyn_tls_init_callback
0x180001285  mov     rbx, rax
0x180001288  cmp     qword ptr [rax], 0
0x18000128c  jz      short loc_1800012AD
0x18000128e  mov     rcx, rax
0x180001291  call    __scrt_is_nonwritable_in_current_image
0x180001296  test    al, al
0x180001298  jz      short loc_1800012AD
0x18000129a  mov     r8, rsi
0x18000129d  mov     edx, 2
0x1800012a2  mov     rcx, r14
0x1800012a5  mov     rax, [rbx]
0x1800012a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012ad  inc     cs:dword_18001E630
0x1800012b3  mov     eax, 1
0x1800012b8  jmp     short loc_1800012BC
0x1800012ba  xor     eax, eax
0x1800012bc  add     rsp, 28h
0x1800012c0  pop     r14
0x1800012c2  pop     rdi
0x1800012c3  pop     rsi
0x1800012c4  pop     rbx
0x1800012c5  retn
0x1800012c6  mov     ecx, 7
0x1800012cb  call    __scrt_fastfail
0x180014950  push    rbp
0x180014952  sub     rsp, 20h
0x180014956  mov     rbp, rdx
0x180014959  mov     cl, [rbp+60h]
0x18001495c  add     rsp, 20h
0x180014960  pop     rbp
0x180014961  jmp     __scrt_release_startup_lock
```
