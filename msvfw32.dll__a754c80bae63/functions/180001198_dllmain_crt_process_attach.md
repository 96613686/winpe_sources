# dllmain_crt_process_attach

- ea: `0x180001198`
- end: `0x180001292`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001140`

## callees

- `0x180001198`
- `0x1800015bc`
- `0x1800015e4`
- `0x180001608`
- `0x180001648`
- `0x180001684`
- `0x180001784`
- `0x180001858`
- `0x1800018f8`
- `0x180001954`
- `0x180001964`
- `0x180001970`
- `0x180001cc6`
- `0x180001cd2`
- `0x180017010`

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
  ++dword_180023CD0;
  return 1;
}

```

## disassembly

```asm
0x180001198  push    rbx
0x18000119a  push    rsi
0x18000119b  push    rdi
0x18000119c  push    r14
0x18000119e  sub     rsp, 28h
0x1800011a2  mov     rsi, rdx
0x1800011a5  mov     r14, rcx
0x1800011a8  xor     ecx, ecx
0x1800011aa  call    __scrt_initialize_crt
0x1800011af  test    al, al
0x1800011b1  jz      loc_18000127A
0x1800011b7  call    __scrt_acquire_startup_lock
0x1800011bc  mov     bl, al
0x1800011be  mov     [rsp+48h+arg_10], al
0x1800011c2  mov     dil, 1
0x1800011c5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800011cc  jnz     loc_180001286
0x1800011d2  mov     cs:__scrt_current_native_startup_state, 1
0x1800011dc  call    __scrt_dllmain_before_initialize_c
0x1800011e1  test    al, al
0x1800011e3  jz      short loc_180001234
0x1800011e5  call    _RTC_Initialize
0x1800011ea  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800011ef  call    __scrt_initialize_default_local_stdio_options
0x1800011f4  lea     rdx, __xi_z; Last
0x1800011fb  lea     rcx, __xi_a; First
0x180001202  call    _initterm_e_0
0x180001207  test    eax, eax
0x180001209  jnz     short loc_180001234
0x18000120b  call    __scrt_dllmain_after_initialize_c
0x180001210  test    al, al
0x180001212  jz      short loc_180001234
0x180001214  lea     rdx, __xc_z; Last
0x18000121b  lea     rcx, __xc_a; First
0x180001222  call    _initterm_0
0x180001227  mov     cs:__scrt_current_native_startup_state, 2
0x180001231  xor     dil, dil
0x180001234  mov     cl, bl
0x180001236  call    __scrt_release_startup_lock
0x18000123b  test    dil, dil
0x18000123e  jnz     short loc_18000127A
0x180001240  call    __scrt_get_dyn_tls_init_callback
0x180001245  mov     rbx, rax
0x180001248  cmp     qword ptr [rax], 0
0x18000124c  jz      short loc_18000126D
0x18000124e  mov     rcx, rax
0x180001251  call    __scrt_is_nonwritable_in_current_image
0x180001256  test    al, al
0x180001258  jz      short loc_18000126D
0x18000125a  mov     r8, rsi
0x18000125d  mov     edx, 2
0x180001262  mov     rcx, r14
0x180001265  mov     rax, [rbx]
0x180001268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000126d  inc     cs:dword_180023CD0
0x180001273  mov     eax, 1
0x180001278  jmp     short loc_18000127C
0x18000127a  xor     eax, eax
0x18000127c  add     rsp, 28h
0x180001280  pop     r14
0x180001282  pop     rdi
0x180001283  pop     rsi
0x180001284  pop     rbx
0x180001285  retn
0x180001286  mov     ecx, 7
0x18000128b  call    __scrt_fastfail
0x18001637c  push    rbp
0x18001637e  sub     rsp, 20h
0x180016382  mov     rbp, rdx
0x180016385  mov     cl, [rbp+60h]
0x180016388  add     rsp, 20h
0x18001638c  pop     rbp
0x18001638d  jmp     __scrt_release_startup_lock
```
