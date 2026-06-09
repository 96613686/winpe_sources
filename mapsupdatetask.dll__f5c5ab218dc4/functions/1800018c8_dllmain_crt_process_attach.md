# dllmain_crt_process_attach

- ea: `0x1800018c8`
- end: `0x1800019c2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001870`

## callees

- `0x1800018c8`
- `0x180001c48`
- `0x180001c88`
- `0x180001cc4`
- `0x180001dc4`
- `0x180001e98`
- `0x180001f38`
- `0x1800020e8`
- `0x180002110`
- `0x180002134`
- `0x180002144`
- `0x180002150`
- `0x180002516`
- `0x180002522`
- `0x180009010`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_attach(__int64 a1, __int64 a2)
{
  char v4; // bl
  char v5; // di
  void (__fastcall **dyn_tls_init_callback)(__int64, __int64, __int64); // rax
  void (__fastcall **v7)(__int64, __int64, __int64); // rbx

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
  _scrt_release_startup_lock(v4);
  if ( v5 )
    return 0;
  dyn_tls_init_callback = (void (__fastcall **)(__int64, __int64, __int64))_scrt_get_dyn_tls_init_callback();
  v7 = dyn_tls_init_callback;
  if ( *dyn_tls_init_callback )
  {
    if ( (unsigned __int8)_scrt_is_nonwritable_in_current_image(dyn_tls_init_callback) )
      (*v7)(a1, 2, a2);
  }
  ++dword_18000E230;
  return 1;
}

```

## disassembly

```asm
0x1800018c8  push    rbx
0x1800018ca  push    rsi
0x1800018cb  push    rdi
0x1800018cc  push    r14
0x1800018ce  sub     rsp, 28h
0x1800018d2  mov     rsi, rdx
0x1800018d5  mov     r14, rcx
0x1800018d8  xor     ecx, ecx
0x1800018da  call    __scrt_initialize_crt
0x1800018df  test    al, al
0x1800018e1  jz      loc_1800019AA
0x1800018e7  call    __scrt_acquire_startup_lock
0x1800018ec  mov     bl, al
0x1800018ee  mov     [rsp+48h+arg_10], al
0x1800018f2  mov     dil, 1
0x1800018f5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800018fc  jnz     loc_1800019B6
0x180001902  mov     cs:__scrt_current_native_startup_state, 1
0x18000190c  call    __scrt_dllmain_before_initialize_c
0x180001911  test    al, al
0x180001913  jz      short loc_180001964
0x180001915  call    _RTC_Initialize
0x18000191a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000191f  call    __scrt_initialize_default_local_stdio_options
0x180001924  lea     rdx, __xi_z; Last
0x18000192b  lea     rcx, __xi_a; First
0x180001932  call    _initterm_e_0
0x180001937  test    eax, eax
0x180001939  jnz     short loc_180001964
0x18000193b  call    __scrt_dllmain_after_initialize_c
0x180001940  test    al, al
0x180001942  jz      short loc_180001964
0x180001944  lea     rdx, __xc_z; Last
0x18000194b  lea     rcx, __xc_a; First
0x180001952  call    _initterm_0
0x180001957  mov     cs:__scrt_current_native_startup_state, 2
0x180001961  xor     dil, dil
0x180001964  mov     cl, bl
0x180001966  call    __scrt_release_startup_lock
0x18000196b  test    dil, dil
0x18000196e  jnz     short loc_1800019AA
0x180001970  call    __scrt_get_dyn_tls_init_callback
0x180001975  mov     rbx, rax
0x180001978  cmp     qword ptr [rax], 0
0x18000197c  jz      short loc_18000199D
0x18000197e  mov     rcx, rax
0x180001981  call    __scrt_is_nonwritable_in_current_image
0x180001986  test    al, al
0x180001988  jz      short loc_18000199D
0x18000198a  mov     r8, rsi
0x18000198d  mov     edx, 2
0x180001992  mov     rcx, r14
0x180001995  mov     rax, [rbx]
0x180001998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000199d  inc     cs:dword_18000E230
0x1800019a3  mov     eax, 1
0x1800019a8  jmp     short loc_1800019AC
0x1800019aa  xor     eax, eax
0x1800019ac  add     rsp, 28h
0x1800019b0  pop     r14
0x1800019b2  pop     rdi
0x1800019b3  pop     rsi
0x1800019b4  pop     rbx
0x1800019b5  retn
0x1800019b6  mov     ecx, 7
0x1800019bb  call    __scrt_fastfail
0x180007f3c  push    rbp
0x180007f3e  sub     rsp, 20h
0x180007f42  mov     rbp, rdx
0x180007f45  mov     cl, [rbp+60h]
0x180007f48  add     rsp, 20h
0x180007f4c  pop     rbp
0x180007f4d  jmp     __scrt_release_startup_lock
```
