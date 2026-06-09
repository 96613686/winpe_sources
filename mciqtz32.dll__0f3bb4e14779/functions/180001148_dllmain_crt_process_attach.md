# dllmain_crt_process_attach

- ea: `0x180001148`
- end: `0x180001242`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800010f0`

## callees

- `0x180001148`
- `0x18000156c`
- `0x180001594`
- `0x1800015b8`
- `0x1800015f8`
- `0x180001634`
- `0x180001734`
- `0x180001808`
- `0x1800018a8`
- `0x180001904`
- `0x180001914`
- `0x180001920`
- `0x180001c86`
- `0x180001c92`
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
  ++dword_18000A090;
  return 1;
}

```

## disassembly

```asm
0x180001148  push    rbx
0x18000114a  push    rsi
0x18000114b  push    rdi
0x18000114c  push    r14
0x18000114e  sub     rsp, 28h
0x180001152  mov     rsi, rdx
0x180001155  mov     r14, rcx
0x180001158  xor     ecx, ecx
0x18000115a  call    __scrt_initialize_crt
0x18000115f  test    al, al
0x180001161  jz      loc_18000122A
0x180001167  call    __scrt_acquire_startup_lock
0x18000116c  mov     bl, al
0x18000116e  mov     [rsp+48h+arg_10], al
0x180001172  mov     dil, 1
0x180001175  cmp     cs:__scrt_current_native_startup_state, 0
0x18000117c  jnz     loc_180001236
0x180001182  mov     cs:__scrt_current_native_startup_state, 1
0x18000118c  call    __scrt_dllmain_before_initialize_c
0x180001191  test    al, al
0x180001193  jz      short loc_1800011E4
0x180001195  call    _RTC_Initialize
0x18000119a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000119f  call    __scrt_initialize_default_local_stdio_options
0x1800011a4  lea     rdx, __xi_z; Last
0x1800011ab  lea     rcx, __xi_a; First
0x1800011b2  call    _initterm_e_0
0x1800011b7  test    eax, eax
0x1800011b9  jnz     short loc_1800011E4
0x1800011bb  call    __scrt_dllmain_after_initialize_c
0x1800011c0  test    al, al
0x1800011c2  jz      short loc_1800011E4
0x1800011c4  lea     rdx, __xc_z; Last
0x1800011cb  lea     rcx, __xc_a; First
0x1800011d2  call    _initterm_0
0x1800011d7  mov     cs:__scrt_current_native_startup_state, 2
0x1800011e1  xor     dil, dil
0x1800011e4  mov     cl, bl
0x1800011e6  call    __scrt_release_startup_lock
0x1800011eb  test    dil, dil
0x1800011ee  jnz     short loc_18000122A
0x1800011f0  call    __scrt_get_dyn_tls_init_callback
0x1800011f5  mov     rbx, rax
0x1800011f8  cmp     qword ptr [rax], 0
0x1800011fc  jz      short loc_18000121D
0x1800011fe  mov     rcx, rax
0x180001201  call    __scrt_is_nonwritable_in_current_image
0x180001206  test    al, al
0x180001208  jz      short loc_18000121D
0x18000120a  mov     r8, rsi
0x18000120d  mov     edx, 2
0x180001212  mov     rcx, r14
0x180001215  mov     rax, [rbx]
0x180001218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000121d  inc     cs:dword_18000A090
0x180001223  mov     eax, 1
0x180001228  jmp     short loc_18000122C
0x18000122a  xor     eax, eax
0x18000122c  add     rsp, 28h
0x180001230  pop     r14
0x180001232  pop     rdi
0x180001233  pop     rsi
0x180001234  pop     rbx
0x180001235  retn
0x180001236  mov     ecx, 7
0x18000123b  call    __scrt_fastfail
0x1800065dc  push    rbp
0x1800065de  sub     rsp, 20h
0x1800065e2  mov     rbp, rdx
0x1800065e5  mov     cl, [rbp+60h]
0x1800065e8  add     rsp, 20h
0x1800065ec  pop     rbp
0x1800065ed  jmp     __scrt_release_startup_lock
```
