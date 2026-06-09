# dllmain_crt_process_attach

- ea: `0x180001268`
- end: `0x180001362`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001210`

## callees

- `0x180001268`
- `0x180001660`
- `0x180001688`
- `0x1800016ac`
- `0x1800016ec`
- `0x180001728`
- `0x180001828`
- `0x1800018fc`
- `0x18000199c`
- `0x180001a58`
- `0x180001a68`
- `0x180001a74`
- `0x180001dd6`
- `0x180001de2`
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
  ++dword_180024750;
  return 1;
}

```

## disassembly

```asm
0x180001268  push    rbx
0x18000126a  push    rsi
0x18000126b  push    rdi
0x18000126c  push    r14
0x18000126e  sub     rsp, 28h
0x180001272  mov     rsi, rdx
0x180001275  mov     r14, rcx
0x180001278  xor     ecx, ecx
0x18000127a  call    __scrt_initialize_crt
0x18000127f  test    al, al
0x180001281  jz      loc_18000134A
0x180001287  call    __scrt_acquire_startup_lock
0x18000128c  mov     bl, al
0x18000128e  mov     [rsp+48h+arg_10], al
0x180001292  mov     dil, 1
0x180001295  cmp     cs:__scrt_current_native_startup_state, 0
0x18000129c  jnz     loc_180001356
0x1800012a2  mov     cs:__scrt_current_native_startup_state, 1
0x1800012ac  call    __scrt_dllmain_before_initialize_c
0x1800012b1  test    al, al
0x1800012b3  jz      short loc_180001304
0x1800012b5  call    _RTC_Initialize
0x1800012ba  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800012bf  call    __scrt_initialize_default_local_stdio_options
0x1800012c4  lea     rdx, __xi_z; Last
0x1800012cb  lea     rcx, __xi_a; First
0x1800012d2  call    _initterm_e_0
0x1800012d7  test    eax, eax
0x1800012d9  jnz     short loc_180001304
0x1800012db  call    __scrt_dllmain_after_initialize_c
0x1800012e0  test    al, al
0x1800012e2  jz      short loc_180001304
0x1800012e4  lea     rdx, __xc_z; Last
0x1800012eb  lea     rcx, __xc_a; First
0x1800012f2  call    _initterm_0
0x1800012f7  mov     cs:__scrt_current_native_startup_state, 2
0x180001301  xor     dil, dil
0x180001304  mov     cl, bl
0x180001306  call    __scrt_release_startup_lock
0x18000130b  test    dil, dil
0x18000130e  jnz     short loc_18000134A
0x180001310  call    __scrt_get_dyn_tls_init_callback
0x180001315  mov     rbx, rax
0x180001318  cmp     qword ptr [rax], 0
0x18000131c  jz      short loc_18000133D
0x18000131e  mov     rcx, rax
0x180001321  call    __scrt_is_nonwritable_in_current_image
0x180001326  test    al, al
0x180001328  jz      short loc_18000133D
0x18000132a  mov     r8, rsi
0x18000132d  mov     edx, 2
0x180001332  mov     rcx, r14
0x180001335  mov     rax, [rbx]
0x180001338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000133d  inc     cs:dword_180024750
0x180001343  mov     eax, 1
0x180001348  jmp     short loc_18000134C
0x18000134a  xor     eax, eax
0x18000134c  add     rsp, 28h
0x180001350  pop     r14
0x180001352  pop     rdi
0x180001353  pop     rsi
0x180001354  pop     rbx
0x180001355  retn
0x180001356  mov     ecx, 7
0x18000135b  call    __scrt_fastfail
0x18001d3dc  push    rbp
0x18001d3de  sub     rsp, 20h
0x18001d3e2  mov     rbp, rdx
0x18001d3e5  mov     cl, [rbp+60h]
0x18001d3e8  add     rsp, 20h
0x18001d3ec  pop     rbp
0x18001d3ed  jmp     __scrt_release_startup_lock
```
