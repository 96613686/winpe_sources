# dllmain_crt_process_attach

- ea: `0x180002388`
- end: `0x180002499`
- name: `dllmain_crt_process_attach`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180002330`

## callees

- `0x180002388`
- `0x18000273c`
- `0x18000277c`
- `0x1800027b8`
- `0x1800028dc`
- `0x1800029b0`
- `0x180002a50`
- `0x180002c10`
- `0x180002c38`
- `0x180002c5c`
- `0x180002c7c`
- `0x180002de4`
- `0x180003246`
- `0x180003252`
- `0x180024010`

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
  {
    _scrt_fastfail(7);
    __debugbreak();
    JUMPOUT(0x180002499LL);
  }
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
  ++dword_180030490;
  return 1;
}

```

## disassembly

```asm
0x180002388  mov     [rsp+arg_0], rbx
0x18000238d  mov     [rsp+arg_8], rsi
0x180002392  mov     [rsp+arg_18], rdi
0x180002397  push    r14
0x180002399  sub     rsp, 20h
0x18000239d  mov     rsi, rdx
0x1800023a0  mov     r14, rcx
0x1800023a3  xor     ecx, ecx
0x1800023a5  call    __scrt_initialize_crt
0x1800023aa  test    al, al
0x1800023ac  jz      loc_180002475
0x1800023b2  call    __scrt_acquire_startup_lock
0x1800023b7  mov     bl, al
0x1800023b9  mov     [rsp+28h+arg_10], al
0x1800023bd  mov     dil, 1
0x1800023c0  cmp     cs:__scrt_current_native_startup_state, 0
0x1800023c7  jnz     loc_18000248D
0x1800023cd  mov     cs:__scrt_current_native_startup_state, 1
0x1800023d7  call    __scrt_dllmain_before_initialize_c
0x1800023dc  test    al, al
0x1800023de  jz      short loc_18000242F
0x1800023e0  call    _RTC_Initialize
0x1800023e5  call    ?__scrt_initialize_type_info@@YAXXZ
0x1800023ea  call    __scrt_initialize_default_local_stdio_options
0x1800023ef  lea     rdx, __xi_z; Last
0x1800023f6  lea     rcx, __xi_a; First
0x1800023fd  call    _initterm_e_0
0x180002402  test    eax, eax
0x180002404  jnz     short loc_18000242F
0x180002406  call    __scrt_dllmain_after_initialize_c
0x18000240b  test    al, al
0x18000240d  jz      short loc_18000242F
0x18000240f  lea     rdx, __xc_z; Last
0x180002416  lea     rcx, __xc_a; First
0x18000241d  call    _initterm_0
0x180002422  mov     cs:__scrt_current_native_startup_state, 2
0x18000242c  xor     dil, dil
0x18000242f  mov     cl, bl
0x180002431  call    __scrt_release_startup_lock
0x180002436  test    dil, dil
0x180002439  jnz     short loc_180002475
0x18000243b  call    __scrt_get_dyn_tls_init_callback
0x180002440  mov     rbx, rax
0x180002443  cmp     qword ptr [rax], 0
0x180002447  jz      short loc_180002468
0x180002449  mov     rcx, rax
0x18000244c  call    __scrt_is_nonwritable_in_current_image
0x180002451  test    al, al
0x180002453  jz      short loc_180002468
0x180002455  mov     r8, rsi
0x180002458  mov     edx, 2
0x18000245d  mov     rcx, r14
0x180002460  mov     rax, [rbx]
0x180002463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002468  inc     cs:dword_180030490
0x18000246e  mov     eax, 1
0x180002473  jmp     short loc_180002477
0x180002475  xor     eax, eax
0x180002477  mov     rbx, [rsp+28h+arg_0]
0x18000247c  mov     rsi, [rsp+28h+arg_8]
0x180002481  mov     rdi, [rsp+28h+arg_18]
0x180002486  add     rsp, 20h
0x18000248a  pop     r14
0x18000248c  retn
0x18000248d  mov     ecx, 7
0x180002492  call    __scrt_fastfail
0x180002497  nop
0x180002498  int     3; Trap to Debugger
0x18002207c  push    rbp
0x18002207e  sub     rsp, 20h
0x180022082  mov     rbp, rdx
0x180022085  mov     cl, [rbp+40h]
0x180022088  add     rsp, 20h
0x18002208c  pop     rbp
0x18002208d  jmp     __scrt_release_startup_lock
```
