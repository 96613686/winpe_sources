# dllmain_crt_process_attach

- ea: `0x180001888`
- end: `0x180001982`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001830`

## callees

- `0x180001888`
- `0x180001bc4`
- `0x180001c04`
- `0x180001c40`
- `0x180001d40`
- `0x180001e14`
- `0x180001eb4`
- `0x18000243c`
- `0x180002464`
- `0x180002488`
- `0x180002498`
- `0x1800024a4`
- `0x180002856`
- `0x180002862`
- `0x18000e010`

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
  ++dword_180018590;
  return 1;
}

```

## disassembly

```asm
0x180001888  push    rbx
0x18000188a  push    rsi
0x18000188b  push    rdi
0x18000188c  push    r14
0x18000188e  sub     rsp, 28h
0x180001892  mov     rsi, rdx
0x180001895  mov     r14, rcx
0x180001898  xor     ecx, ecx
0x18000189a  call    __scrt_initialize_crt
0x18000189f  test    al, al
0x1800018a1  jz      loc_18000196A
0x1800018a7  call    __scrt_acquire_startup_lock
0x1800018ac  mov     bl, al
0x1800018ae  mov     [rsp+48h+arg_10], al
0x1800018b2  mov     dil, 1
0x1800018b5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800018bc  jnz     loc_180001976
0x1800018c2  mov     cs:__scrt_current_native_startup_state, 1
0x1800018cc  call    __scrt_dllmain_before_initialize_c
0x1800018d1  test    al, al
0x1800018d3  jz      short loc_180001924
0x1800018d5  call    _RTC_Initialize
0x1800018da  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800018df  call    __scrt_initialize_default_local_stdio_options
0x1800018e4  lea     rdx, __xi_z; Last
0x1800018eb  lea     rcx, __xi_a; First
0x1800018f2  call    _initterm_e_0
0x1800018f7  test    eax, eax
0x1800018f9  jnz     short loc_180001924
0x1800018fb  call    __scrt_dllmain_after_initialize_c
0x180001900  test    al, al
0x180001902  jz      short loc_180001924
0x180001904  lea     rdx, __xc_z; Last
0x18000190b  lea     rcx, __xc_a; First
0x180001912  call    _initterm_0
0x180001917  mov     cs:__scrt_current_native_startup_state, 2
0x180001921  xor     dil, dil
0x180001924  mov     cl, bl
0x180001926  call    __scrt_release_startup_lock
0x18000192b  test    dil, dil
0x18000192e  jnz     short loc_18000196A
0x180001930  call    __scrt_get_dyn_tls_init_callback
0x180001935  mov     rbx, rax
0x180001938  cmp     qword ptr [rax], 0
0x18000193c  jz      short loc_18000195D
0x18000193e  mov     rcx, rax
0x180001941  call    __scrt_is_nonwritable_in_current_image
0x180001946  test    al, al
0x180001948  jz      short loc_18000195D
0x18000194a  mov     r8, rsi
0x18000194d  mov     edx, 2
0x180001952  mov     rcx, r14
0x180001955  mov     rax, [rbx]
0x180001958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000195d  inc     cs:dword_180018590
0x180001963  mov     eax, 1
0x180001968  jmp     short loc_18000196C
0x18000196a  xor     eax, eax
0x18000196c  add     rsp, 28h
0x180001970  pop     r14
0x180001972  pop     rdi
0x180001973  pop     rsi
0x180001974  pop     rbx
0x180001975  retn
0x180001976  mov     ecx, 7
0x18000197b  call    __scrt_fastfail
0x18000d63c  push    rbp
0x18000d63e  sub     rsp, 20h
0x18000d642  mov     rbp, rdx
0x18000d645  mov     cl, [rbp+60h]
0x18000d648  add     rsp, 20h
0x18000d64c  pop     rbp
0x18000d64d  jmp     __scrt_release_startup_lock
```
