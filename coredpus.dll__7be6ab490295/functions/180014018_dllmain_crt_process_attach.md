# dllmain_crt_process_attach

- ea: `0x180014018`
- end: `0x180014112`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180013fc0`

## callees

- `0x180014018`
- `0x1800147ac`
- `0x1800147d4`
- `0x1800147f8`
- `0x180014838`
- `0x180014874`
- `0x180014974`
- `0x180014a48`
- `0x180014ae8`
- `0x180014ba4`
- `0x180014bb4`
- `0x180014bc0`
- `0x18001501c`
- `0x180015028`
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
  ++dword_18003E990;
  return 1;
}

```

## disassembly

```asm
0x180014018  push    rbx
0x18001401a  push    rsi
0x18001401b  push    rdi
0x18001401c  push    r14
0x18001401e  sub     rsp, 28h
0x180014022  mov     rsi, rdx
0x180014025  mov     r14, rcx
0x180014028  xor     ecx, ecx
0x18001402a  call    __scrt_initialize_crt
0x18001402f  test    al, al
0x180014031  jz      loc_1800140FA
0x180014037  call    __scrt_acquire_startup_lock
0x18001403c  mov     bl, al
0x18001403e  mov     [rsp+48h+arg_10], al
0x180014042  mov     dil, 1
0x180014045  cmp     cs:__scrt_current_native_startup_state, 0
0x18001404c  jnz     loc_180014106
0x180014052  mov     cs:__scrt_current_native_startup_state, 1
0x18001405c  call    __scrt_dllmain_before_initialize_c
0x180014061  test    al, al
0x180014063  jz      short loc_1800140B4
0x180014065  call    _RTC_Initialize
0x18001406a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18001406f  call    __scrt_initialize_default_local_stdio_options
0x180014074  lea     rdx, __xi_z; Last
0x18001407b  lea     rcx, __xi_a; First
0x180014082  call    _initterm_e_0
0x180014087  test    eax, eax
0x180014089  jnz     short loc_1800140B4
0x18001408b  call    __scrt_dllmain_after_initialize_c
0x180014090  test    al, al
0x180014092  jz      short loc_1800140B4
0x180014094  lea     rdx, __xc_z; Last
0x18001409b  lea     rcx, __xc_a; First
0x1800140a2  call    _initterm_0
0x1800140a7  mov     cs:__scrt_current_native_startup_state, 2
0x1800140b1  xor     dil, dil
0x1800140b4  mov     cl, bl
0x1800140b6  call    __scrt_release_startup_lock
0x1800140bb  test    dil, dil
0x1800140be  jnz     short loc_1800140FA
0x1800140c0  call    __scrt_get_dyn_tls_init_callback
0x1800140c5  mov     rbx, rax
0x1800140c8  cmp     qword ptr [rax], 0
0x1800140cc  jz      short loc_1800140ED
0x1800140ce  mov     rcx, rax
0x1800140d1  call    __scrt_is_nonwritable_in_current_image
0x1800140d6  test    al, al
0x1800140d8  jz      short loc_1800140ED
0x1800140da  mov     r8, rsi
0x1800140dd  mov     edx, 2
0x1800140e2  mov     rcx, r14
0x1800140e5  mov     rax, [rbx]
0x1800140e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140ed  inc     cs:dword_18003E990
0x1800140f3  mov     eax, 1
0x1800140f8  jmp     short loc_1800140FC
0x1800140fa  xor     eax, eax
0x1800140fc  add     rsp, 28h
0x180014100  pop     r14
0x180014102  pop     rdi
0x180014103  pop     rsi
0x180014104  pop     rbx
0x180014105  retn
0x180014106  mov     ecx, 7
0x18001410b  call    __scrt_fastfail
0x18002e708  push    rbp
0x18002e70a  sub     rsp, 20h
0x18002e70e  mov     rbp, rdx
0x18002e711  mov     cl, [rbp+60h]
0x18002e714  add     rsp, 20h
0x18002e718  pop     rbp
0x18002e719  jmp     __scrt_release_startup_lock
```
