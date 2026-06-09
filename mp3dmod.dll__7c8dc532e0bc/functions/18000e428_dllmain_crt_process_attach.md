# dllmain_crt_process_attach

- ea: `0x18000e428`
- end: `0x18000e522`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x18000e3d0`

## callees

- `0x18000e428`
- `0x18000e7fc`
- `0x18000e824`
- `0x18000e848`
- `0x18000e888`
- `0x18000e8c4`
- `0x18000e9c4`
- `0x18000ea98`
- `0x18000eb38`
- `0x18000eb94`
- `0x18000eba4`
- `0x18000ebb0`
- `0x18000ef06`
- `0x18000ef12`
- `0x180012010`

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
  ++dword_18001B110;
  return 1;
}

```

## disassembly

```asm
0x18000e428  push    rbx
0x18000e42a  push    rsi
0x18000e42b  push    rdi
0x18000e42c  push    r14
0x18000e42e  sub     rsp, 28h
0x18000e432  mov     rsi, rdx
0x18000e435  mov     r14, rcx
0x18000e438  xor     ecx, ecx
0x18000e43a  call    __scrt_initialize_crt
0x18000e43f  test    al, al
0x18000e441  jz      loc_18000E50A
0x18000e447  call    __scrt_acquire_startup_lock
0x18000e44c  mov     bl, al
0x18000e44e  mov     [rsp+48h+arg_10], al
0x18000e452  mov     dil, 1
0x18000e455  cmp     cs:__scrt_current_native_startup_state, 0
0x18000e45c  jnz     loc_18000E516
0x18000e462  mov     cs:__scrt_current_native_startup_state, 1
0x18000e46c  call    __scrt_dllmain_before_initialize_c
0x18000e471  test    al, al
0x18000e473  jz      short loc_18000E4C4
0x18000e475  call    _RTC_Initialize
0x18000e47a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000e47f  call    __scrt_initialize_default_local_stdio_options
0x18000e484  lea     rdx, __xi_z; Last
0x18000e48b  lea     rcx, __xi_a; First
0x18000e492  call    _initterm_e_0
0x18000e497  test    eax, eax
0x18000e499  jnz     short loc_18000E4C4
0x18000e49b  call    __scrt_dllmain_after_initialize_c
0x18000e4a0  test    al, al
0x18000e4a2  jz      short loc_18000E4C4
0x18000e4a4  lea     rdx, __xc_z; Last
0x18000e4ab  lea     rcx, __xc_a; First
0x18000e4b2  call    _initterm_0
0x18000e4b7  mov     cs:__scrt_current_native_startup_state, 2
0x18000e4c1  xor     dil, dil
0x18000e4c4  mov     cl, bl
0x18000e4c6  call    __scrt_release_startup_lock
0x18000e4cb  test    dil, dil
0x18000e4ce  jnz     short loc_18000E50A
0x18000e4d0  call    __scrt_get_dyn_tls_init_callback
0x18000e4d5  mov     rbx, rax
0x18000e4d8  cmp     qword ptr [rax], 0
0x18000e4dc  jz      short loc_18000E4FD
0x18000e4de  mov     rcx, rax
0x18000e4e1  call    __scrt_is_nonwritable_in_current_image
0x18000e4e6  test    al, al
0x18000e4e8  jz      short loc_18000E4FD
0x18000e4ea  mov     r8, rsi
0x18000e4ed  mov     edx, 2
0x18000e4f2  mov     rcx, r14
0x18000e4f5  mov     rax, [rbx]
0x18000e4f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4fd  inc     cs:dword_18001B110
0x18000e503  mov     eax, 1
0x18000e508  jmp     short loc_18000E50C
0x18000e50a  xor     eax, eax
0x18000e50c  add     rsp, 28h
0x18000e510  pop     r14
0x18000e512  pop     rdi
0x18000e513  pop     rsi
0x18000e514  pop     rbx
0x18000e515  retn
0x18000e516  mov     ecx, 7
0x18000e51b  call    __scrt_fastfail
0x18001153c  push    rbp
0x18001153e  sub     rsp, 20h
0x180011542  mov     rbp, rdx
0x180011545  mov     cl, [rbp+60h]
0x180011548  add     rsp, 20h
0x18001154c  pop     rbp
0x18001154d  jmp     __scrt_release_startup_lock
```
