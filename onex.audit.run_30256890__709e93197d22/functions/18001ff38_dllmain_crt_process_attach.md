# dllmain_crt_process_attach

- ea: `0x18001ff38`
- end: `0x180020032`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x18001fee0`

## callees

- `0x18001ff38`
- `0x180020358`
- `0x180020380`
- `0x1800203a4`
- `0x1800203e4`
- `0x180020420`
- `0x180020520`
- `0x1800205f4`
- `0x180020694`
- `0x1800206f0`
- `0x180020700`
- `0x18002070c`
- `0x180020a66`
- `0x180020a72`
- `0x180030010`

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
  ++dword_18003A290;
  return 1;
}

```

## disassembly

```asm
0x18001ff38  push    rbx
0x18001ff3a  push    rsi
0x18001ff3b  push    rdi
0x18001ff3c  push    r14
0x18001ff3e  sub     rsp, 28h
0x18001ff42  mov     rsi, rdx
0x18001ff45  mov     r14, rcx
0x18001ff48  xor     ecx, ecx
0x18001ff4a  call    __scrt_initialize_crt
0x18001ff4f  test    al, al
0x18001ff51  jz      loc_18002001A
0x18001ff57  call    __scrt_acquire_startup_lock
0x18001ff5c  mov     bl, al
0x18001ff5e  mov     [rsp+48h+arg_10], al
0x18001ff62  mov     dil, 1
0x18001ff65  cmp     cs:__scrt_current_native_startup_state, 0
0x18001ff6c  jnz     loc_180020026
0x18001ff72  mov     cs:__scrt_current_native_startup_state, 1
0x18001ff7c  call    __scrt_dllmain_before_initialize_c
0x18001ff81  test    al, al
0x18001ff83  jz      short loc_18001FFD4
0x18001ff85  call    _RTC_Initialize
0x18001ff8a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18001ff8f  call    __scrt_initialize_default_local_stdio_options
0x18001ff94  lea     rdx, __xi_z; Last
0x18001ff9b  lea     rcx, __xi_a; First
0x18001ffa2  call    _initterm_e_0
0x18001ffa7  test    eax, eax
0x18001ffa9  jnz     short loc_18001FFD4
0x18001ffab  call    __scrt_dllmain_after_initialize_c
0x18001ffb0  test    al, al
0x18001ffb2  jz      short loc_18001FFD4
0x18001ffb4  lea     rdx, __xc_z; Last
0x18001ffbb  lea     rcx, __xc_a; First
0x18001ffc2  call    _initterm_0
0x18001ffc7  mov     cs:__scrt_current_native_startup_state, 2
0x18001ffd1  xor     dil, dil
0x18001ffd4  mov     cl, bl
0x18001ffd6  call    __scrt_release_startup_lock
0x18001ffdb  test    dil, dil
0x18001ffde  jnz     short loc_18002001A
0x18001ffe0  call    __scrt_get_dyn_tls_init_callback
0x18001ffe5  mov     rbx, rax
0x18001ffe8  cmp     qword ptr [rax], 0
0x18001ffec  jz      short loc_18002000D
0x18001ffee  mov     rcx, rax
0x18001fff1  call    __scrt_is_nonwritable_in_current_image
0x18001fff6  test    al, al
0x18001fff8  jz      short loc_18002000D
0x18001fffa  mov     r8, rsi
0x18001fffd  mov     edx, 2
0x180020002  mov     rcx, r14
0x180020005  mov     rax, [rbx]
0x180020008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002000d  inc     cs:dword_18003A290
0x180020013  mov     eax, 1
0x180020018  jmp     short loc_18002001C
0x18002001a  xor     eax, eax
0x18002001c  add     rsp, 28h
0x180020020  pop     r14
0x180020022  pop     rdi
0x180020023  pop     rsi
0x180020024  pop     rbx
0x180020025  retn
0x180020026  mov     ecx, 7
0x18002002b  call    __scrt_fastfail
0x18002f77c  push    rbp
0x18002f77e  sub     rsp, 20h
0x18002f782  mov     rbp, rdx
0x18002f785  mov     cl, [rbp+60h]
0x18002f788  add     rsp, 20h
0x18002f78c  pop     rbp
0x18002f78d  jmp     __scrt_release_startup_lock
```
