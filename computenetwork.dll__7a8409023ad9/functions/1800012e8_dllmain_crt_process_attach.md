# dllmain_crt_process_attach

- ea: `0x1800012e8`
- end: `0x1800013e2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001290`

## callees

- `0x1800012e8`
- `0x180001624`
- `0x180001664`
- `0x1800016a0`
- `0x1800017a0`
- `0x180001874`
- `0x180001914`
- `0x180001b38`
- `0x180001b60`
- `0x180001b84`
- `0x180001b94`
- `0x180001ba0`
- `0x180001f66`
- `0x180001f72`
- `0x18000f010`

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
  ++dword_180018270;
  return 1;
}

```

## disassembly

```asm
0x1800012e8  push    rbx
0x1800012ea  push    rsi
0x1800012eb  push    rdi
0x1800012ec  push    r14
0x1800012ee  sub     rsp, 28h
0x1800012f2  mov     rsi, rdx
0x1800012f5  mov     r14, rcx
0x1800012f8  xor     ecx, ecx
0x1800012fa  call    __scrt_initialize_crt
0x1800012ff  test    al, al
0x180001301  jz      loc_1800013CA
0x180001307  call    __scrt_acquire_startup_lock
0x18000130c  mov     bl, al
0x18000130e  mov     [rsp+48h+arg_10], al
0x180001312  mov     dil, 1
0x180001315  cmp     cs:__scrt_current_native_startup_state, 0
0x18000131c  jnz     loc_1800013D6
0x180001322  mov     cs:__scrt_current_native_startup_state, 1
0x18000132c  call    __scrt_dllmain_before_initialize_c
0x180001331  test    al, al
0x180001333  jz      short loc_180001384
0x180001335  call    _RTC_Initialize
0x18000133a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000133f  call    __scrt_initialize_default_local_stdio_options
0x180001344  lea     rdx, __xi_z; Last
0x18000134b  lea     rcx, __xi_a; First
0x180001352  call    _initterm_e_0
0x180001357  test    eax, eax
0x180001359  jnz     short loc_180001384
0x18000135b  call    __scrt_dllmain_after_initialize_c
0x180001360  test    al, al
0x180001362  jz      short loc_180001384
0x180001364  lea     rdx, __xc_z; Last
0x18000136b  lea     rcx, __xc_a; First
0x180001372  call    _initterm_0
0x180001377  mov     cs:__scrt_current_native_startup_state, 2
0x180001381  xor     dil, dil
0x180001384  mov     cl, bl
0x180001386  call    __scrt_release_startup_lock
0x18000138b  test    dil, dil
0x18000138e  jnz     short loc_1800013CA
0x180001390  call    __scrt_get_dyn_tls_init_callback
0x180001395  mov     rbx, rax
0x180001398  cmp     qword ptr [rax], 0
0x18000139c  jz      short loc_1800013BD
0x18000139e  mov     rcx, rax
0x1800013a1  call    __scrt_is_nonwritable_in_current_image
0x1800013a6  test    al, al
0x1800013a8  jz      short loc_1800013BD
0x1800013aa  mov     r8, rsi
0x1800013ad  mov     edx, 2
0x1800013b2  mov     rcx, r14
0x1800013b5  mov     rax, [rbx]
0x1800013b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800013bd  inc     cs:dword_180018270
0x1800013c3  mov     eax, 1
0x1800013c8  jmp     short loc_1800013CC
0x1800013ca  xor     eax, eax
0x1800013cc  add     rsp, 28h
0x1800013d0  pop     r14
0x1800013d2  pop     rdi
0x1800013d3  pop     rsi
0x1800013d4  pop     rbx
0x1800013d5  retn
0x1800013d6  mov     ecx, 7
0x1800013db  call    __scrt_fastfail
0x18000cf5c  push    rbp
0x18000cf5e  sub     rsp, 20h
0x18000cf62  mov     rbp, rdx
0x18000cf65  mov     cl, [rbp+60h]
0x18000cf68  add     rsp, 20h
0x18000cf6c  pop     rbp
0x18000cf6d  jmp     __scrt_release_startup_lock
```
