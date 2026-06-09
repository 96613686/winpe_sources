# dllmain_crt_process_attach

- ea: `0x180001248`
- end: `0x180001342`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800011f0`

## callees

- `0x180001248`
- `0x180001640`
- `0x180001668`
- `0x18000168c`
- `0x1800016cc`
- `0x180001708`
- `0x180001808`
- `0x1800018dc`
- `0x18000197c`
- `0x180001a38`
- `0x180001a48`
- `0x180001a54`
- `0x180001db6`
- `0x180001dc2`
- `0x180016010`

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
  ++dword_18001D1D0;
  return 1;
}

```

## disassembly

```asm
0x180001248  push    rbx
0x18000124a  push    rsi
0x18000124b  push    rdi
0x18000124c  push    r14
0x18000124e  sub     rsp, 28h
0x180001252  mov     rsi, rdx
0x180001255  mov     r14, rcx
0x180001258  xor     ecx, ecx
0x18000125a  call    __scrt_initialize_crt
0x18000125f  test    al, al
0x180001261  jz      loc_18000132A
0x180001267  call    __scrt_acquire_startup_lock
0x18000126c  mov     bl, al
0x18000126e  mov     [rsp+48h+arg_10], al
0x180001272  mov     dil, 1
0x180001275  cmp     cs:__scrt_current_native_startup_state, 0
0x18000127c  jnz     loc_180001336
0x180001282  mov     cs:__scrt_current_native_startup_state, 1
0x18000128c  call    __scrt_dllmain_before_initialize_c
0x180001291  test    al, al
0x180001293  jz      short loc_1800012E4
0x180001295  call    _RTC_Initialize
0x18000129a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000129f  call    __scrt_initialize_default_local_stdio_options
0x1800012a4  lea     rdx, __xi_z; Last
0x1800012ab  lea     rcx, __xi_a; First
0x1800012b2  call    _initterm_e_0
0x1800012b7  test    eax, eax
0x1800012b9  jnz     short loc_1800012E4
0x1800012bb  call    __scrt_dllmain_after_initialize_c
0x1800012c0  test    al, al
0x1800012c2  jz      short loc_1800012E4
0x1800012c4  lea     rdx, __xc_z; Last
0x1800012cb  lea     rcx, __xc_a; First
0x1800012d2  call    _initterm_0
0x1800012d7  mov     cs:__scrt_current_native_startup_state, 2
0x1800012e1  xor     dil, dil
0x1800012e4  mov     cl, bl
0x1800012e6  call    __scrt_release_startup_lock
0x1800012eb  test    dil, dil
0x1800012ee  jnz     short loc_18000132A
0x1800012f0  call    __scrt_get_dyn_tls_init_callback
0x1800012f5  mov     rbx, rax
0x1800012f8  cmp     qword ptr [rax], 0
0x1800012fc  jz      short loc_18000131D
0x1800012fe  mov     rcx, rax
0x180001301  call    __scrt_is_nonwritable_in_current_image
0x180001306  test    al, al
0x180001308  jz      short loc_18000131D
0x18000130a  mov     r8, rsi
0x18000130d  mov     edx, 2
0x180001312  mov     rcx, r14
0x180001315  mov     rax, [rbx]
0x180001318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000131d  inc     cs:dword_18001D1D0
0x180001323  mov     eax, 1
0x180001328  jmp     short loc_18000132C
0x18000132a  xor     eax, eax
0x18000132c  add     rsp, 28h
0x180001330  pop     r14
0x180001332  pop     rdi
0x180001333  pop     rsi
0x180001334  pop     rbx
0x180001335  retn
0x180001336  mov     ecx, 7
0x18000133b  call    __scrt_fastfail
0x1800158bc  push    rbp
0x1800158be  sub     rsp, 20h
0x1800158c2  mov     rbp, rdx
0x1800158c5  mov     cl, [rbp+60h]
0x1800158c8  add     rsp, 20h
0x1800158cc  pop     rbp
0x1800158cd  jmp     __scrt_release_startup_lock
```
