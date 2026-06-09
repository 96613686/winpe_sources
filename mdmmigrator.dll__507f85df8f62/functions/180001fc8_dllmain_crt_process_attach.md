# dllmain_crt_process_attach

- ea: `0x180001fc8`
- end: `0x1800020c2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001f70`

## callees

- `0x180001fc8`
- `0x180002304`
- `0x180002344`
- `0x180002380`
- `0x180002480`
- `0x180002554`
- `0x1800025f4`
- `0x1800027a8`
- `0x1800027d0`
- `0x1800027f4`
- `0x180002804`
- `0x180002810`
- `0x180002b76`
- `0x180002b82`
- `0x180020010`

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
  ++dword_18002B550;
  return 1;
}

```

## disassembly

```asm
0x180001fc8  push    rbx
0x180001fca  push    rsi
0x180001fcb  push    rdi
0x180001fcc  push    r14
0x180001fce  sub     rsp, 28h
0x180001fd2  mov     rsi, rdx
0x180001fd5  mov     r14, rcx
0x180001fd8  xor     ecx, ecx
0x180001fda  call    __scrt_initialize_crt
0x180001fdf  test    al, al
0x180001fe1  jz      loc_1800020AA
0x180001fe7  call    __scrt_acquire_startup_lock
0x180001fec  mov     bl, al
0x180001fee  mov     [rsp+48h+arg_10], al
0x180001ff2  mov     dil, 1
0x180001ff5  cmp     cs:__scrt_current_native_startup_state, 0
0x180001ffc  jnz     loc_1800020B6
0x180002002  mov     cs:__scrt_current_native_startup_state, 1
0x18000200c  call    __scrt_dllmain_before_initialize_c
0x180002011  test    al, al
0x180002013  jz      short loc_180002064
0x180002015  call    _RTC_Initialize
0x18000201a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000201f  call    __scrt_initialize_default_local_stdio_options
0x180002024  lea     rdx, __xi_z; Last
0x18000202b  lea     rcx, __xi_a; First
0x180002032  call    _initterm_e_0
0x180002037  test    eax, eax
0x180002039  jnz     short loc_180002064
0x18000203b  call    __scrt_dllmain_after_initialize_c
0x180002040  test    al, al
0x180002042  jz      short loc_180002064
0x180002044  lea     rdx, __xc_z; Last
0x18000204b  lea     rcx, __xc_a; First
0x180002052  call    _initterm_0
0x180002057  mov     cs:__scrt_current_native_startup_state, 2
0x180002061  xor     dil, dil
0x180002064  mov     cl, bl
0x180002066  call    __scrt_release_startup_lock
0x18000206b  test    dil, dil
0x18000206e  jnz     short loc_1800020AA
0x180002070  call    __scrt_get_dyn_tls_init_callback
0x180002075  mov     rbx, rax
0x180002078  cmp     qword ptr [rax], 0
0x18000207c  jz      short loc_18000209D
0x18000207e  mov     rcx, rax
0x180002081  call    __scrt_is_nonwritable_in_current_image
0x180002086  test    al, al
0x180002088  jz      short loc_18000209D
0x18000208a  mov     r8, rsi
0x18000208d  mov     edx, 2
0x180002092  mov     rcx, r14
0x180002095  mov     rax, [rbx]
0x180002098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000209d  inc     cs:dword_18002B550
0x1800020a3  mov     eax, 1
0x1800020a8  jmp     short loc_1800020AC
0x1800020aa  xor     eax, eax
0x1800020ac  add     rsp, 28h
0x1800020b0  pop     r14
0x1800020b2  pop     rdi
0x1800020b3  pop     rsi
0x1800020b4  pop     rbx
0x1800020b5  retn
0x1800020b6  mov     ecx, 7
0x1800020bb  call    __scrt_fastfail
0x18001eacc  push    rbp
0x18001eace  sub     rsp, 20h
0x18001ead2  mov     rbp, rdx
0x18001ead5  mov     cl, [rbp+60h]
0x18001ead8  add     rsp, 20h
0x18001eadc  pop     rbp
0x18001eadd  jmp     __scrt_release_startup_lock
```
