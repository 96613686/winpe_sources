# dllmain_crt_process_attach

- ea: `0x18000b0e8`
- end: `0x18000b1e2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x18000b090`

## callees

- `0x18000b0e8`
- `0x18000b434`
- `0x18000b474`
- `0x18000b4b0`
- `0x18000b5b0`
- `0x18000b684`
- `0x18000b724`
- `0x18000b928`
- `0x18000b950`
- `0x18000b974`
- `0x18000b984`
- `0x18000b990`
- `0x18000bd56`
- `0x18000bd62`
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
  ++dword_18001C510;
  return 1;
}

```

## disassembly

```asm
0x18000b0e8  push    rbx
0x18000b0ea  push    rsi
0x18000b0eb  push    rdi
0x18000b0ec  push    r14
0x18000b0ee  sub     rsp, 28h
0x18000b0f2  mov     rsi, rdx
0x18000b0f5  mov     r14, rcx
0x18000b0f8  xor     ecx, ecx
0x18000b0fa  call    __scrt_initialize_crt
0x18000b0ff  test    al, al
0x18000b101  jz      loc_18000B1CA
0x18000b107  call    __scrt_acquire_startup_lock
0x18000b10c  mov     bl, al
0x18000b10e  mov     [rsp+48h+arg_10], al
0x18000b112  mov     dil, 1
0x18000b115  cmp     cs:__scrt_current_native_startup_state, 0
0x18000b11c  jnz     loc_18000B1D6
0x18000b122  mov     cs:__scrt_current_native_startup_state, 1
0x18000b12c  call    __scrt_dllmain_before_initialize_c
0x18000b131  test    al, al
0x18000b133  jz      short loc_18000B184
0x18000b135  call    _RTC_Initialize
0x18000b13a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000b13f  call    __scrt_initialize_default_local_stdio_options
0x18000b144  lea     rdx, __xi_z; Last
0x18000b14b  lea     rcx, __xi_a; First
0x18000b152  call    _initterm_e_0
0x18000b157  test    eax, eax
0x18000b159  jnz     short loc_18000B184
0x18000b15b  call    __scrt_dllmain_after_initialize_c
0x18000b160  test    al, al
0x18000b162  jz      short loc_18000B184
0x18000b164  lea     rdx, __xc_z; Last
0x18000b16b  lea     rcx, __xc_a; First
0x18000b172  call    _initterm_0
0x18000b177  mov     cs:__scrt_current_native_startup_state, 2
0x18000b181  xor     dil, dil
0x18000b184  mov     cl, bl
0x18000b186  call    __scrt_release_startup_lock
0x18000b18b  test    dil, dil
0x18000b18e  jnz     short loc_18000B1CA
0x18000b190  call    __scrt_get_dyn_tls_init_callback
0x18000b195  mov     rbx, rax
0x18000b198  cmp     qword ptr [rax], 0
0x18000b19c  jz      short loc_18000B1BD
0x18000b19e  mov     rcx, rax
0x18000b1a1  call    __scrt_is_nonwritable_in_current_image
0x18000b1a6  test    al, al
0x18000b1a8  jz      short loc_18000B1BD
0x18000b1aa  mov     r8, rsi
0x18000b1ad  mov     edx, 2
0x18000b1b2  mov     rcx, r14
0x18000b1b5  mov     rax, [rbx]
0x18000b1b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1bd  inc     cs:dword_18001C510
0x18000b1c3  mov     eax, 1
0x18000b1c8  jmp     short loc_18000B1CC
0x18000b1ca  xor     eax, eax
0x18000b1cc  add     rsp, 28h
0x18000b1d0  pop     r14
0x18000b1d2  pop     rdi
0x18000b1d3  pop     rsi
0x18000b1d4  pop     rbx
0x18000b1d5  retn
0x18000b1d6  mov     ecx, 7
0x18000b1db  call    __scrt_fastfail
0x180013e2e  push    rbp
0x180013e30  sub     rsp, 20h
0x180013e34  mov     rbp, rdx
0x180013e37  mov     cl, [rbp+60h]
0x180013e3a  add     rsp, 20h
0x180013e3e  pop     rbp
0x180013e3f  jmp     __scrt_release_startup_lock
```
