# dllmain_crt_process_attach

- ea: `0x180001328`
- end: `0x180001422`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800012d0`

## callees

- `0x180001328`
- `0x180001720`
- `0x180001748`
- `0x18000176c`
- `0x1800017ac`
- `0x1800017e8`
- `0x1800018e8`
- `0x1800019bc`
- `0x180001a5c`
- `0x180001b18`
- `0x180001b28`
- `0x180001b34`
- `0x180001e86`
- `0x180001e92`
- `0x180028010`

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
  ++dword_180035610;
  return 1;
}

```

## disassembly

```asm
0x180001328  push    rbx
0x18000132a  push    rsi
0x18000132b  push    rdi
0x18000132c  push    r14
0x18000132e  sub     rsp, 28h
0x180001332  mov     rsi, rdx
0x180001335  mov     r14, rcx
0x180001338  xor     ecx, ecx
0x18000133a  call    __scrt_initialize_crt
0x18000133f  test    al, al
0x180001341  jz      loc_18000140A
0x180001347  call    __scrt_acquire_startup_lock
0x18000134c  mov     bl, al
0x18000134e  mov     [rsp+48h+arg_10], al
0x180001352  mov     dil, 1
0x180001355  cmp     cs:__scrt_current_native_startup_state, 0
0x18000135c  jnz     loc_180001416
0x180001362  mov     cs:__scrt_current_native_startup_state, 1
0x18000136c  call    __scrt_dllmain_before_initialize_c
0x180001371  test    al, al
0x180001373  jz      short loc_1800013C4
0x180001375  call    _RTC_Initialize
0x18000137a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000137f  call    __scrt_initialize_default_local_stdio_options
0x180001384  lea     rdx, __xi_z; Last
0x18000138b  lea     rcx, __xi_a; First
0x180001392  call    _initterm_e_0
0x180001397  test    eax, eax
0x180001399  jnz     short loc_1800013C4
0x18000139b  call    __scrt_dllmain_after_initialize_c
0x1800013a0  test    al, al
0x1800013a2  jz      short loc_1800013C4
0x1800013a4  lea     rdx, __xc_z; Last
0x1800013ab  lea     rcx, __xc_a; First
0x1800013b2  call    _initterm_0
0x1800013b7  mov     cs:__scrt_current_native_startup_state, 2
0x1800013c1  xor     dil, dil
0x1800013c4  mov     cl, bl
0x1800013c6  call    __scrt_release_startup_lock
0x1800013cb  test    dil, dil
0x1800013ce  jnz     short loc_18000140A
0x1800013d0  call    __scrt_get_dyn_tls_init_callback
0x1800013d5  mov     rbx, rax
0x1800013d8  cmp     qword ptr [rax], 0
0x1800013dc  jz      short loc_1800013FD
0x1800013de  mov     rcx, rax
0x1800013e1  call    __scrt_is_nonwritable_in_current_image
0x1800013e6  test    al, al
0x1800013e8  jz      short loc_1800013FD
0x1800013ea  mov     r8, rsi
0x1800013ed  mov     edx, 2
0x1800013f2  mov     rcx, r14
0x1800013f5  mov     rax, [rbx]
0x1800013f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013fd  inc     cs:dword_180035610
0x180001403  mov     eax, 1
0x180001408  jmp     short loc_18000140C
0x18000140a  xor     eax, eax
0x18000140c  add     rsp, 28h
0x180001410  pop     r14
0x180001412  pop     rdi
0x180001413  pop     rsi
0x180001414  pop     rbx
0x180001415  retn
0x180001416  mov     ecx, 7
0x18000141b  call    __scrt_fastfail
0x1800253ec  push    rbp
0x1800253ee  sub     rsp, 20h
0x1800253f2  mov     rbp, rdx
0x1800253f5  mov     cl, [rbp+60h]
0x1800253f8  add     rsp, 20h
0x1800253fc  pop     rbp
0x1800253fd  jmp     __scrt_release_startup_lock
```
