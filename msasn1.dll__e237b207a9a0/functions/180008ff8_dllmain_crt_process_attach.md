# dllmain_crt_process_attach

- ea: `0x180008ff8`
- end: `0x1800090f2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180008fa0`

## callees

- `0x180008ff8`
- `0x1800093f0`
- `0x180009418`
- `0x18000943c`
- `0x18000947c`
- `0x1800094b8`
- `0x1800095b8`
- `0x18000968c`
- `0x18000972c`
- `0x180009788`
- `0x180009798`
- `0x1800097a4`
- `0x180009b06`
- `0x180009b12`
- `0x18000b010`

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
  ++dword_18000F090;
  return 1;
}

```

## disassembly

```asm
0x180008ff8  push    rbx
0x180008ffa  push    rsi
0x180008ffb  push    rdi
0x180008ffc  push    r14
0x180008ffe  sub     rsp, 28h
0x180009002  mov     rsi, rdx
0x180009005  mov     r14, rcx
0x180009008  xor     ecx, ecx
0x18000900a  call    __scrt_initialize_crt
0x18000900f  test    al, al
0x180009011  jz      loc_1800090DA
0x180009017  call    __scrt_acquire_startup_lock
0x18000901c  mov     bl, al
0x18000901e  mov     [rsp+48h+arg_10], al
0x180009022  mov     dil, 1
0x180009025  cmp     cs:__scrt_current_native_startup_state, 0
0x18000902c  jnz     loc_1800090E6
0x180009032  mov     cs:__scrt_current_native_startup_state, 1
0x18000903c  call    __scrt_dllmain_before_initialize_c
0x180009041  test    al, al
0x180009043  jz      short loc_180009094
0x180009045  call    _RTC_Initialize
0x18000904a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000904f  call    __scrt_initialize_default_local_stdio_options
0x180009054  lea     rdx, __xi_z; Last
0x18000905b  lea     rcx, __xi_a; First
0x180009062  call    _initterm_e_0
0x180009067  test    eax, eax
0x180009069  jnz     short loc_180009094
0x18000906b  call    __scrt_dllmain_after_initialize_c
0x180009070  test    al, al
0x180009072  jz      short loc_180009094
0x180009074  lea     rdx, __xc_z; Last
0x18000907b  lea     rcx, __xc_a; First
0x180009082  call    _initterm_0
0x180009087  mov     cs:__scrt_current_native_startup_state, 2
0x180009091  xor     dil, dil
0x180009094  mov     cl, bl
0x180009096  call    __scrt_release_startup_lock
0x18000909b  test    dil, dil
0x18000909e  jnz     short loc_1800090DA
0x1800090a0  call    __scrt_get_dyn_tls_init_callback
0x1800090a5  mov     rbx, rax
0x1800090a8  cmp     qword ptr [rax], 0
0x1800090ac  jz      short loc_1800090CD
0x1800090ae  mov     rcx, rax
0x1800090b1  call    __scrt_is_nonwritable_in_current_image
0x1800090b6  test    al, al
0x1800090b8  jz      short loc_1800090CD
0x1800090ba  mov     r8, rsi
0x1800090bd  mov     edx, 2
0x1800090c2  mov     rcx, r14
0x1800090c5  mov     rax, [rbx]
0x1800090c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090cd  inc     cs:dword_18000F090
0x1800090d3  mov     eax, 1
0x1800090d8  jmp     short loc_1800090DC
0x1800090da  xor     eax, eax
0x1800090dc  add     rsp, 28h
0x1800090e0  pop     r14
0x1800090e2  pop     rdi
0x1800090e3  pop     rsi
0x1800090e4  pop     rbx
0x1800090e5  retn
0x1800090e6  mov     ecx, 7
0x1800090eb  call    __scrt_fastfail
0x18000ab5c  push    rbp
0x18000ab5e  sub     rsp, 20h
0x18000ab62  mov     rbp, rdx
0x18000ab65  mov     cl, [rbp+60h]
0x18000ab68  add     rsp, 20h
0x18000ab6c  pop     rbp
0x18000ab6d  jmp     __scrt_release_startup_lock
```
