# dllmain_crt_process_attach

- ea: `0x180001298`
- end: `0x180001392`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001240`

## callees

- `0x180001298`
- `0x180001718`
- `0x180001740`
- `0x180001764`
- `0x1800017a4`
- `0x1800017e0`
- `0x1800018e0`
- `0x1800019b4`
- `0x180001a54`
- `0x180001b10`
- `0x180001b20`
- `0x180001b2c`
- `0x180001ee6`
- `0x180001ef2`
- `0x18000a010`

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
  ++dword_1800101F0;
  return 1;
}

```

## disassembly

```asm
0x180001298  push    rbx
0x18000129a  push    rsi
0x18000129b  push    rdi
0x18000129c  push    r14
0x18000129e  sub     rsp, 28h
0x1800012a2  mov     rsi, rdx
0x1800012a5  mov     r14, rcx
0x1800012a8  xor     ecx, ecx
0x1800012aa  call    __scrt_initialize_crt
0x1800012af  test    al, al
0x1800012b1  jz      loc_18000137A
0x1800012b7  call    __scrt_acquire_startup_lock
0x1800012bc  mov     bl, al
0x1800012be  mov     [rsp+48h+arg_10], al
0x1800012c2  mov     dil, 1
0x1800012c5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800012cc  jnz     loc_180001386
0x1800012d2  mov     cs:__scrt_current_native_startup_state, 1
0x1800012dc  call    __scrt_dllmain_before_initialize_c
0x1800012e1  test    al, al
0x1800012e3  jz      short loc_180001334
0x1800012e5  call    _RTC_Initialize
0x1800012ea  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800012ef  call    __scrt_initialize_default_local_stdio_options
0x1800012f4  lea     rdx, __xi_z; Last
0x1800012fb  lea     rcx, __xi_a; First
0x180001302  call    _initterm_e_0
0x180001307  test    eax, eax
0x180001309  jnz     short loc_180001334
0x18000130b  call    __scrt_dllmain_after_initialize_c
0x180001310  test    al, al
0x180001312  jz      short loc_180001334
0x180001314  lea     rdx, __xc_z; Last
0x18000131b  lea     rcx, __xc_a; First
0x180001322  call    _initterm_0
0x180001327  mov     cs:__scrt_current_native_startup_state, 2
0x180001331  xor     dil, dil
0x180001334  mov     cl, bl
0x180001336  call    __scrt_release_startup_lock
0x18000133b  test    dil, dil
0x18000133e  jnz     short loc_18000137A
0x180001340  call    __scrt_get_dyn_tls_init_callback
0x180001345  mov     rbx, rax
0x180001348  cmp     qword ptr [rax], 0
0x18000134c  jz      short loc_18000136D
0x18000134e  mov     rcx, rax
0x180001351  call    __scrt_is_nonwritable_in_current_image
0x180001356  test    al, al
0x180001358  jz      short loc_18000136D
0x18000135a  mov     r8, rsi
0x18000135d  mov     edx, 2
0x180001362  mov     rcx, r14
0x180001365  mov     rax, [rbx]
0x180001368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000136d  inc     cs:dword_1800101F0
0x180001373  mov     eax, 1
0x180001378  jmp     short loc_18000137C
0x18000137a  xor     eax, eax
0x18000137c  add     rsp, 28h
0x180001380  pop     r14
0x180001382  pop     rdi
0x180001383  pop     rsi
0x180001384  pop     rbx
0x180001385  retn
0x180001386  mov     ecx, 7
0x18000138b  call    __scrt_fastfail
0x1800095cc  push    rbp
0x1800095ce  sub     rsp, 20h
0x1800095d2  mov     rbp, rdx
0x1800095d5  mov     cl, [rbp+60h]
0x1800095d8  add     rsp, 20h
0x1800095dc  pop     rbp
0x1800095dd  jmp     __scrt_release_startup_lock
```
