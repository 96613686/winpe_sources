# dllmain_crt_process_attach

- ea: `0x1800011e8`
- end: `0x1800012e2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001190`

## callees

- `0x1800011e8`
- `0x180001524`
- `0x180001564`
- `0x1800015a0`
- `0x1800016a0`
- `0x180001774`
- `0x180001814`
- `0x180001a50`
- `0x180001a8c`
- `0x180001ab0`
- `0x180001ac0`
- `0x180001acc`
- `0x1800050b6`
- `0x1800050c2`
- `0x18000d010`

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
  ++dword_180014248;
  return 1;
}

```

## disassembly

```asm
0x1800011e8  push    rbx
0x1800011ea  push    rsi
0x1800011eb  push    rdi
0x1800011ec  push    r14
0x1800011ee  sub     rsp, 28h
0x1800011f2  mov     rsi, rdx
0x1800011f5  mov     r14, rcx
0x1800011f8  xor     ecx, ecx
0x1800011fa  call    __scrt_initialize_crt
0x1800011ff  test    al, al
0x180001201  jz      loc_1800012CA
0x180001207  call    __scrt_acquire_startup_lock
0x18000120c  mov     bl, al
0x18000120e  mov     [rsp+48h+arg_10], al
0x180001212  mov     dil, 1
0x180001215  cmp     cs:__scrt_current_native_startup_state, 0
0x18000121c  jnz     loc_1800012D6
0x180001222  mov     cs:__scrt_current_native_startup_state, 1
0x18000122c  call    __scrt_dllmain_before_initialize_c
0x180001231  test    al, al
0x180001233  jz      short loc_180001284
0x180001235  call    _RTC_Initialize
0x18000123a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000123f  call    __scrt_initialize_default_local_stdio_options
0x180001244  lea     rdx, __xi_z; Last
0x18000124b  lea     rcx, __xi_a; First
0x180001252  call    _initterm_e_0
0x180001257  test    eax, eax
0x180001259  jnz     short loc_180001284
0x18000125b  call    __scrt_dllmain_after_initialize_c
0x180001260  test    al, al
0x180001262  jz      short loc_180001284
0x180001264  lea     rdx, __xc_z; Last
0x18000126b  lea     rcx, __xc_a; First
0x180001272  call    _initterm_0
0x180001277  mov     cs:__scrt_current_native_startup_state, 2
0x180001281  xor     dil, dil
0x180001284  mov     cl, bl
0x180001286  call    __scrt_release_startup_lock
0x18000128b  test    dil, dil
0x18000128e  jnz     short loc_1800012CA
0x180001290  call    __scrt_get_dyn_tls_init_callback
0x180001295  mov     rbx, rax
0x180001298  cmp     qword ptr [rax], 0
0x18000129c  jz      short loc_1800012BD
0x18000129e  mov     rcx, rax
0x1800012a1  call    __scrt_is_nonwritable_in_current_image
0x1800012a6  test    al, al
0x1800012a8  jz      short loc_1800012BD
0x1800012aa  mov     r8, rsi
0x1800012ad  mov     edx, 2
0x1800012b2  mov     rcx, r14
0x1800012b5  mov     rax, [rbx]
0x1800012b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012bd  inc     cs:dword_180014248
0x1800012c3  mov     eax, 1
0x1800012c8  jmp     short loc_1800012CC
0x1800012ca  xor     eax, eax
0x1800012cc  add     rsp, 28h
0x1800012d0  pop     r14
0x1800012d2  pop     rdi
0x1800012d3  pop     rsi
0x1800012d4  pop     rbx
0x1800012d5  retn
0x1800012d6  mov     ecx, 7
0x1800012db  call    __scrt_fastfail
0x18000bc40  push    rbp
0x18000bc42  sub     rsp, 20h
0x18000bc46  mov     rbp, rdx
0x18000bc49  mov     cl, [rbp+60h]
0x18000bc4c  add     rsp, 20h
0x18000bc50  pop     rbp
0x18000bc51  jmp     __scrt_release_startup_lock
```
