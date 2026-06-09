# dllmain_crt_process_attach

- ea: `0x180001228`
- end: `0x180001322`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800011d0`

## callees

- `0x180001228`
- `0x1800015b4`
- `0x1800015f4`
- `0x180001630`
- `0x180001730`
- `0x180001804`
- `0x1800018a4`
- `0x180001a84`
- `0x180001aac`
- `0x180001ad0`
- `0x180001ae0`
- `0x180001aec`
- `0x180001e86`
- `0x180001e92`
- `0x180015010`

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
  ++dword_18001F270;
  return 1;
}

```

## disassembly

```asm
0x180001228  push    rbx
0x18000122a  push    rsi
0x18000122b  push    rdi
0x18000122c  push    r14
0x18000122e  sub     rsp, 28h
0x180001232  mov     rsi, rdx
0x180001235  mov     r14, rcx
0x180001238  xor     ecx, ecx
0x18000123a  call    __scrt_initialize_crt
0x18000123f  test    al, al
0x180001241  jz      loc_18000130A
0x180001247  call    __scrt_acquire_startup_lock
0x18000124c  mov     bl, al
0x18000124e  mov     [rsp+48h+arg_10], al
0x180001252  mov     dil, 1
0x180001255  cmp     cs:__scrt_current_native_startup_state, 0
0x18000125c  jnz     loc_180001316
0x180001262  mov     cs:__scrt_current_native_startup_state, 1
0x18000126c  call    __scrt_dllmain_before_initialize_c
0x180001271  test    al, al
0x180001273  jz      short loc_1800012C4
0x180001275  call    _RTC_Initialize
0x18000127a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000127f  call    __scrt_initialize_default_local_stdio_options
0x180001284  lea     rdx, __xi_z; Last
0x18000128b  lea     rcx, __xi_a; First
0x180001292  call    _initterm_e_0
0x180001297  test    eax, eax
0x180001299  jnz     short loc_1800012C4
0x18000129b  call    __scrt_dllmain_after_initialize_c
0x1800012a0  test    al, al
0x1800012a2  jz      short loc_1800012C4
0x1800012a4  lea     rdx, __xc_z; Last
0x1800012ab  lea     rcx, __xc_a; First
0x1800012b2  call    _initterm_0
0x1800012b7  mov     cs:__scrt_current_native_startup_state, 2
0x1800012c1  xor     dil, dil
0x1800012c4  mov     cl, bl
0x1800012c6  call    __scrt_release_startup_lock
0x1800012cb  test    dil, dil
0x1800012ce  jnz     short loc_18000130A
0x1800012d0  call    __scrt_get_dyn_tls_init_callback
0x1800012d5  mov     rbx, rax
0x1800012d8  cmp     qword ptr [rax], 0
0x1800012dc  jz      short loc_1800012FD
0x1800012de  mov     rcx, rax
0x1800012e1  call    __scrt_is_nonwritable_in_current_image
0x1800012e6  test    al, al
0x1800012e8  jz      short loc_1800012FD
0x1800012ea  mov     r8, rsi
0x1800012ed  mov     edx, 2
0x1800012f2  mov     rcx, r14
0x1800012f5  mov     rax, [rbx]
0x1800012f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012fd  inc     cs:dword_18001F270
0x180001303  mov     eax, 1
0x180001308  jmp     short loc_18000130C
0x18000130a  xor     eax, eax
0x18000130c  add     rsp, 28h
0x180001310  pop     r14
0x180001312  pop     rdi
0x180001313  pop     rsi
0x180001314  pop     rbx
0x180001315  retn
0x180001316  mov     ecx, 7
0x18000131b  call    __scrt_fastfail
0x180013e7c  push    rbp
0x180013e7e  sub     rsp, 20h
0x180013e82  mov     rbp, rdx
0x180013e85  mov     cl, [rbp+60h]
0x180013e88  add     rsp, 20h
0x180013e8c  pop     rbp
0x180013e8d  jmp     __scrt_release_startup_lock
```
