# dllmain_crt_process_attach

- ea: `0x180001748`
- end: `0x180001842`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800016f0`

## callees

- `0x180001748`
- `0x180001c4c`
- `0x180001c74`
- `0x180001c98`
- `0x180001cd8`
- `0x180001d14`
- `0x180001e14`
- `0x180001ee8`
- `0x180001f88`
- `0x180002044`
- `0x180002054`
- `0x180002060`
- `0x180002436`
- `0x180002442`
- `0x180012010`

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
  ++dword_18001C650;
  return 1;
}

```

## disassembly

```asm
0x180001748  push    rbx
0x18000174a  push    rsi
0x18000174b  push    rdi
0x18000174c  push    r14
0x18000174e  sub     rsp, 28h
0x180001752  mov     rsi, rdx
0x180001755  mov     r14, rcx
0x180001758  xor     ecx, ecx
0x18000175a  call    __scrt_initialize_crt
0x18000175f  test    al, al
0x180001761  jz      loc_18000182A
0x180001767  call    __scrt_acquire_startup_lock
0x18000176c  mov     bl, al
0x18000176e  mov     [rsp+48h+arg_10], al
0x180001772  mov     dil, 1
0x180001775  cmp     cs:__scrt_current_native_startup_state, 0
0x18000177c  jnz     loc_180001836
0x180001782  mov     cs:__scrt_current_native_startup_state, 1
0x18000178c  call    __scrt_dllmain_before_initialize_c
0x180001791  test    al, al
0x180001793  jz      short loc_1800017E4
0x180001795  call    _RTC_Initialize
0x18000179a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000179f  call    __scrt_initialize_default_local_stdio_options
0x1800017a4  lea     rdx, __xi_z; Last
0x1800017ab  lea     rcx, __xi_a; First
0x1800017b2  call    _initterm_e_0
0x1800017b7  test    eax, eax
0x1800017b9  jnz     short loc_1800017E4
0x1800017bb  call    __scrt_dllmain_after_initialize_c
0x1800017c0  test    al, al
0x1800017c2  jz      short loc_1800017E4
0x1800017c4  lea     rdx, __xc_z; Last
0x1800017cb  lea     rcx, __xc_a; First
0x1800017d2  call    _initterm_0
0x1800017d7  mov     cs:__scrt_current_native_startup_state, 2
0x1800017e1  xor     dil, dil
0x1800017e4  mov     cl, bl
0x1800017e6  call    __scrt_release_startup_lock
0x1800017eb  test    dil, dil
0x1800017ee  jnz     short loc_18000182A
0x1800017f0  call    __scrt_get_dyn_tls_init_callback
0x1800017f5  mov     rbx, rax
0x1800017f8  cmp     qword ptr [rax], 0
0x1800017fc  jz      short loc_18000181D
0x1800017fe  mov     rcx, rax
0x180001801  call    __scrt_is_nonwritable_in_current_image
0x180001806  test    al, al
0x180001808  jz      short loc_18000181D
0x18000180a  mov     r8, rsi
0x18000180d  mov     edx, 2
0x180001812  mov     rcx, r14
0x180001815  mov     rax, [rbx]
0x180001818  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000181d  inc     cs:dword_18001C650
0x180001823  mov     eax, 1
0x180001828  jmp     short loc_18000182C
0x18000182a  xor     eax, eax
0x18000182c  add     rsp, 28h
0x180001830  pop     r14
0x180001832  pop     rdi
0x180001833  pop     rsi
0x180001834  pop     rbx
0x180001835  retn
0x180001836  mov     ecx, 7
0x18000183b  call    __scrt_fastfail
0x18001177c  push    rbp
0x18001177e  sub     rsp, 20h
0x180011782  mov     rbp, rdx
0x180011785  mov     cl, [rbp+60h]
0x180011788  add     rsp, 20h
0x18001178c  pop     rbp
0x18001178d  jmp     __scrt_release_startup_lock
```
