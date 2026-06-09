# dllmain_crt_process_attach

- ea: `0x1800014c8`
- end: `0x1800015c2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001470`

## callees

- `0x1800014c8`
- `0x180001930`
- `0x180001970`
- `0x1800019ac`
- `0x180001aac`
- `0x180001b80`
- `0x180001c20`
- `0x180001de8`
- `0x180001e10`
- `0x180001e34`
- `0x180001e44`
- `0x180001e50`
- `0x180002256`
- `0x180002262`
- `0x180026010`

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
  ++dword_180033D10;
  return 1;
}

```

## disassembly

```asm
0x1800014c8  push    rbx
0x1800014ca  push    rsi
0x1800014cb  push    rdi
0x1800014cc  push    r14
0x1800014ce  sub     rsp, 28h
0x1800014d2  mov     rsi, rdx
0x1800014d5  mov     r14, rcx
0x1800014d8  xor     ecx, ecx
0x1800014da  call    __scrt_initialize_crt
0x1800014df  test    al, al
0x1800014e1  jz      loc_1800015AA
0x1800014e7  call    __scrt_acquire_startup_lock
0x1800014ec  mov     bl, al
0x1800014ee  mov     [rsp+48h+arg_10], al
0x1800014f2  mov     dil, 1
0x1800014f5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800014fc  jnz     loc_1800015B6
0x180001502  mov     cs:__scrt_current_native_startup_state, 1
0x18000150c  call    __scrt_dllmain_before_initialize_c
0x180001511  test    al, al
0x180001513  jz      short loc_180001564
0x180001515  call    _RTC_Initialize
0x18000151a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000151f  call    __scrt_initialize_default_local_stdio_options
0x180001524  lea     rdx, __xi_z; Last
0x18000152b  lea     rcx, __xi_a; First
0x180001532  call    _initterm_e_0
0x180001537  test    eax, eax
0x180001539  jnz     short loc_180001564
0x18000153b  call    __scrt_dllmain_after_initialize_c
0x180001540  test    al, al
0x180001542  jz      short loc_180001564
0x180001544  lea     rdx, __xc_z; Last
0x18000154b  lea     rcx, __xc_a; First
0x180001552  call    _initterm_0
0x180001557  mov     cs:__scrt_current_native_startup_state, 2
0x180001561  xor     dil, dil
0x180001564  mov     cl, bl
0x180001566  call    __scrt_release_startup_lock
0x18000156b  test    dil, dil
0x18000156e  jnz     short loc_1800015AA
0x180001570  call    __scrt_get_dyn_tls_init_callback
0x180001575  mov     rbx, rax
0x180001578  cmp     qword ptr [rax], 0
0x18000157c  jz      short loc_18000159D
0x18000157e  mov     rcx, rax
0x180001581  call    __scrt_is_nonwritable_in_current_image
0x180001586  test    al, al
0x180001588  jz      short loc_18000159D
0x18000158a  mov     r8, rsi
0x18000158d  mov     edx, 2
0x180001592  mov     rcx, r14
0x180001595  mov     rax, [rbx]
0x180001598  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000159d  inc     cs:dword_180033D10
0x1800015a3  mov     eax, 1
0x1800015a8  jmp     short loc_1800015AC
0x1800015aa  xor     eax, eax
0x1800015ac  add     rsp, 28h
0x1800015b0  pop     r14
0x1800015b2  pop     rdi
0x1800015b3  pop     rsi
0x1800015b4  pop     rbx
0x1800015b5  retn
0x1800015b6  mov     ecx, 7
0x1800015bb  call    __scrt_fastfail
0x18002445c  push    rbp
0x18002445e  sub     rsp, 20h
0x180024462  mov     rbp, rdx
0x180024465  mov     cl, [rbp+60h]
0x180024468  add     rsp, 20h
0x18002446c  pop     rbp
0x18002446d  jmp     __scrt_release_startup_lock
```
