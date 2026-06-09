# dllmain_crt_process_attach

- ea: `0x180001208`
- end: `0x180001302`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800011b0`

## callees

- `0x180001208`
- `0x180001544`
- `0x180001584`
- `0x1800015c0`
- `0x1800016c0`
- `0x180001794`
- `0x180001834`
- `0x180001a64`
- `0x180001a8c`
- `0x180001ab0`
- `0x180001ac0`
- `0x180001acc`
- `0x180001e96`
- `0x180001ea2`
- `0x18000c010`

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
  ++dword_180011250;
  return 1;
}

```

## disassembly

```asm
0x180001208  push    rbx
0x18000120a  push    rsi
0x18000120b  push    rdi
0x18000120c  push    r14
0x18000120e  sub     rsp, 28h
0x180001212  mov     rsi, rdx
0x180001215  mov     r14, rcx
0x180001218  xor     ecx, ecx
0x18000121a  call    __scrt_initialize_crt
0x18000121f  test    al, al
0x180001221  jz      loc_1800012EA
0x180001227  call    __scrt_acquire_startup_lock
0x18000122c  mov     bl, al
0x18000122e  mov     [rsp+48h+arg_10], al
0x180001232  mov     dil, 1
0x180001235  cmp     cs:__scrt_current_native_startup_state, 0
0x18000123c  jnz     loc_1800012F6
0x180001242  mov     cs:__scrt_current_native_startup_state, 1
0x18000124c  call    __scrt_dllmain_before_initialize_c
0x180001251  test    al, al
0x180001253  jz      short loc_1800012A4
0x180001255  call    _RTC_Initialize
0x18000125a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000125f  call    __scrt_initialize_default_local_stdio_options
0x180001264  lea     rdx, __xi_z; Last
0x18000126b  lea     rcx, __xi_a; First
0x180001272  call    _initterm_e_0
0x180001277  test    eax, eax
0x180001279  jnz     short loc_1800012A4
0x18000127b  call    __scrt_dllmain_after_initialize_c
0x180001280  test    al, al
0x180001282  jz      short loc_1800012A4
0x180001284  lea     rdx, __xc_z; Last
0x18000128b  lea     rcx, __xc_a; First
0x180001292  call    _initterm_0
0x180001297  mov     cs:__scrt_current_native_startup_state, 2
0x1800012a1  xor     dil, dil
0x1800012a4  mov     cl, bl
0x1800012a6  call    __scrt_release_startup_lock
0x1800012ab  test    dil, dil
0x1800012ae  jnz     short loc_1800012EA
0x1800012b0  call    __scrt_get_dyn_tls_init_callback
0x1800012b5  mov     rbx, rax
0x1800012b8  cmp     qword ptr [rax], 0
0x1800012bc  jz      short loc_1800012DD
0x1800012be  mov     rcx, rax
0x1800012c1  call    __scrt_is_nonwritable_in_current_image
0x1800012c6  test    al, al
0x1800012c8  jz      short loc_1800012DD
0x1800012ca  mov     r8, rsi
0x1800012cd  mov     edx, 2
0x1800012d2  mov     rcx, r14
0x1800012d5  mov     rax, [rbx]
0x1800012d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012dd  inc     cs:dword_180011250
0x1800012e3  mov     eax, 1
0x1800012e8  jmp     short loc_1800012EC
0x1800012ea  xor     eax, eax
0x1800012ec  add     rsp, 28h
0x1800012f0  pop     r14
0x1800012f2  pop     rdi
0x1800012f3  pop     rsi
0x1800012f4  pop     rbx
0x1800012f5  retn
0x1800012f6  mov     ecx, 7
0x1800012fb  call    __scrt_fastfail
0x18000a92c  push    rbp
0x18000a92e  sub     rsp, 20h
0x18000a932  mov     rbp, rdx
0x18000a935  mov     cl, [rbp+60h]
0x18000a938  add     rsp, 20h
0x18000a93c  pop     rbp
0x18000a93d  jmp     __scrt_release_startup_lock
```
