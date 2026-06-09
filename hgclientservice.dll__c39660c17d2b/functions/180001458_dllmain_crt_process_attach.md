# dllmain_crt_process_attach

- ea: `0x180001458`
- end: `0x180001552`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001400`

## callees

- `0x180001458`
- `0x1800017fc`
- `0x18000183c`
- `0x180001878`
- `0x180001978`
- `0x180001a4c`
- `0x180001aec`
- `0x180001ca8`
- `0x180001cd0`
- `0x180001cf4`
- `0x180001d04`
- `0x180001d10`
- `0x1800020c6`
- `0x1800020d2`
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
  ++dword_1800202D0;
  return 1;
}

```

## disassembly

```asm
0x180001458  push    rbx
0x18000145a  push    rsi
0x18000145b  push    rdi
0x18000145c  push    r14
0x18000145e  sub     rsp, 28h
0x180001462  mov     rsi, rdx
0x180001465  mov     r14, rcx
0x180001468  xor     ecx, ecx
0x18000146a  call    __scrt_initialize_crt
0x18000146f  test    al, al
0x180001471  jz      loc_18000153A
0x180001477  call    __scrt_acquire_startup_lock
0x18000147c  mov     bl, al
0x18000147e  mov     [rsp+48h+arg_10], al
0x180001482  mov     dil, 1
0x180001485  cmp     cs:__scrt_current_native_startup_state, 0
0x18000148c  jnz     loc_180001546
0x180001492  mov     cs:__scrt_current_native_startup_state, 1
0x18000149c  call    __scrt_dllmain_before_initialize_c
0x1800014a1  test    al, al
0x1800014a3  jz      short loc_1800014F4
0x1800014a5  call    _RTC_Initialize
0x1800014aa  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800014af  call    __scrt_initialize_default_local_stdio_options
0x1800014b4  lea     rdx, __xi_z; Last
0x1800014bb  lea     rcx, __xi_a; First
0x1800014c2  call    _initterm_e_0
0x1800014c7  test    eax, eax
0x1800014c9  jnz     short loc_1800014F4
0x1800014cb  call    __scrt_dllmain_after_initialize_c
0x1800014d0  test    al, al
0x1800014d2  jz      short loc_1800014F4
0x1800014d4  lea     rdx, __xc_z; Last
0x1800014db  lea     rcx, __xc_a; First
0x1800014e2  call    _initterm_0
0x1800014e7  mov     cs:__scrt_current_native_startup_state, 2
0x1800014f1  xor     dil, dil
0x1800014f4  mov     cl, bl
0x1800014f6  call    __scrt_release_startup_lock
0x1800014fb  test    dil, dil
0x1800014fe  jnz     short loc_18000153A
0x180001500  call    __scrt_get_dyn_tls_init_callback
0x180001505  mov     rbx, rax
0x180001508  cmp     qword ptr [rax], 0
0x18000150c  jz      short loc_18000152D
0x18000150e  mov     rcx, rax
0x180001511  call    __scrt_is_nonwritable_in_current_image
0x180001516  test    al, al
0x180001518  jz      short loc_18000152D
0x18000151a  mov     r8, rsi
0x18000151d  mov     edx, 2
0x180001522  mov     rcx, r14
0x180001525  mov     rax, [rbx]
0x180001528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000152d  inc     cs:dword_1800202D0
0x180001533  mov     eax, 1
0x180001538  jmp     short loc_18000153C
0x18000153a  xor     eax, eax
0x18000153c  add     rsp, 28h
0x180001540  pop     r14
0x180001542  pop     rdi
0x180001543  pop     rsi
0x180001544  pop     rbx
0x180001545  retn
0x180001546  mov     ecx, 7
0x18000154b  call    __scrt_fastfail
0x18001529c  push    rbp
0x18001529e  sub     rsp, 20h
0x1800152a2  mov     rbp, rdx
0x1800152a5  mov     cl, [rbp+60h]
0x1800152a8  add     rsp, 20h
0x1800152ac  pop     rbp
0x1800152ad  jmp     __scrt_release_startup_lock
```
