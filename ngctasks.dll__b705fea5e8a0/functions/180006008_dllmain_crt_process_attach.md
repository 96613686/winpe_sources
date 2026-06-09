# dllmain_crt_process_attach

- ea: `0x180006008`
- end: `0x180006102`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180005fb0`

## callees

- `0x180006008`
- `0x180006448`
- `0x180006488`
- `0x1800064c4`
- `0x1800065c4`
- `0x180006698`
- `0x180006738`
- `0x18000692c`
- `0x180006954`
- `0x180006978`
- `0x180006988`
- `0x180006994`
- `0x180006d66`
- `0x180006d72`
- `0x180022010`

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
  ++dword_180031330;
  return 1;
}

```

## disassembly

```asm
0x180006008  push    rbx
0x18000600a  push    rsi
0x18000600b  push    rdi
0x18000600c  push    r14
0x18000600e  sub     rsp, 28h
0x180006012  mov     rsi, rdx
0x180006015  mov     r14, rcx
0x180006018  xor     ecx, ecx
0x18000601a  call    __scrt_initialize_crt
0x18000601f  test    al, al
0x180006021  jz      loc_1800060EA
0x180006027  call    __scrt_acquire_startup_lock
0x18000602c  mov     bl, al
0x18000602e  mov     [rsp+48h+arg_10], al
0x180006032  mov     dil, 1
0x180006035  cmp     cs:__scrt_current_native_startup_state, 0
0x18000603c  jnz     loc_1800060F6
0x180006042  mov     cs:__scrt_current_native_startup_state, 1
0x18000604c  call    __scrt_dllmain_before_initialize_c
0x180006051  test    al, al
0x180006053  jz      short loc_1800060A4
0x180006055  call    _RTC_Initialize
0x18000605a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000605f  call    __scrt_initialize_default_local_stdio_options
0x180006064  lea     rdx, __xi_z; Last
0x18000606b  lea     rcx, __xi_a; First
0x180006072  call    _initterm_e_0
0x180006077  test    eax, eax
0x180006079  jnz     short loc_1800060A4
0x18000607b  call    __scrt_dllmain_after_initialize_c
0x180006080  test    al, al
0x180006082  jz      short loc_1800060A4
0x180006084  lea     rdx, __xc_z; Last
0x18000608b  lea     rcx, __xc_a; First
0x180006092  call    _initterm_0
0x180006097  mov     cs:__scrt_current_native_startup_state, 2
0x1800060a1  xor     dil, dil
0x1800060a4  mov     cl, bl
0x1800060a6  call    __scrt_release_startup_lock
0x1800060ab  test    dil, dil
0x1800060ae  jnz     short loc_1800060EA
0x1800060b0  call    __scrt_get_dyn_tls_init_callback
0x1800060b5  mov     rbx, rax
0x1800060b8  cmp     qword ptr [rax], 0
0x1800060bc  jz      short loc_1800060DD
0x1800060be  mov     rcx, rax
0x1800060c1  call    __scrt_is_nonwritable_in_current_image
0x1800060c6  test    al, al
0x1800060c8  jz      short loc_1800060DD
0x1800060ca  mov     r8, rsi
0x1800060cd  mov     edx, 2
0x1800060d2  mov     rcx, r14
0x1800060d5  mov     rax, [rbx]
0x1800060d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060dd  inc     cs:dword_180031330
0x1800060e3  mov     eax, 1
0x1800060e8  jmp     short loc_1800060EC
0x1800060ea  xor     eax, eax
0x1800060ec  add     rsp, 28h
0x1800060f0  pop     r14
0x1800060f2  pop     rdi
0x1800060f3  pop     rsi
0x1800060f4  pop     rbx
0x1800060f5  retn
0x1800060f6  mov     ecx, 7
0x1800060fb  call    __scrt_fastfail
0x18001e9fc  push    rbp
0x18001e9fe  sub     rsp, 20h
0x18001ea02  mov     rbp, rdx
0x18001ea05  mov     cl, [rbp+60h]
0x18001ea08  add     rsp, 20h
0x18001ea0c  pop     rbp
0x18001ea0d  jmp     __scrt_release_startup_lock
```
