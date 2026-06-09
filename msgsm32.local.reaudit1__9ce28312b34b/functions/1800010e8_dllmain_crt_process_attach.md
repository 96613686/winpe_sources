# dllmain_crt_process_attach

- ea: `0x1800010e8`
- end: `0x1800011e2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001090`

## callees

- `0x1800010e8`
- `0x180001538`
- `0x180001560`
- `0x180001584`
- `0x1800015c4`
- `0x180001600`
- `0x180001700`
- `0x1800017d4`
- `0x180001874`
- `0x1800018d0`
- `0x1800018e0`
- `0x1800018ec`
- `0x180001c46`
- `0x180001c52`
- `0x180007010`

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
  ++dword_18000A0D0;
  return 1;
}

```

## disassembly

```asm
0x1800010e8  push    rbx
0x1800010ea  push    rsi
0x1800010eb  push    rdi
0x1800010ec  push    r14
0x1800010ee  sub     rsp, 28h
0x1800010f2  mov     rsi, rdx
0x1800010f5  mov     r14, rcx
0x1800010f8  xor     ecx, ecx
0x1800010fa  call    __scrt_initialize_crt
0x1800010ff  test    al, al
0x180001101  jz      loc_1800011CA
0x180001107  call    __scrt_acquire_startup_lock
0x18000110c  mov     bl, al
0x18000110e  mov     [rsp+48h+arg_10], al
0x180001112  mov     dil, 1
0x180001115  cmp     cs:__scrt_current_native_startup_state, 0
0x18000111c  jnz     loc_1800011D6
0x180001122  mov     cs:__scrt_current_native_startup_state, 1
0x18000112c  call    __scrt_dllmain_before_initialize_c
0x180001131  test    al, al
0x180001133  jz      short loc_180001184
0x180001135  call    _RTC_Initialize
0x18000113a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000113f  call    __scrt_initialize_default_local_stdio_options
0x180001144  lea     rdx, __xi_z; Last
0x18000114b  lea     rcx, __xi_a; First
0x180001152  call    _initterm_e_0
0x180001157  test    eax, eax
0x180001159  jnz     short loc_180001184
0x18000115b  call    __scrt_dllmain_after_initialize_c
0x180001160  test    al, al
0x180001162  jz      short loc_180001184
0x180001164  lea     rdx, __xc_z; Last
0x18000116b  lea     rcx, __xc_a; First
0x180001172  call    _initterm_0
0x180001177  mov     cs:__scrt_current_native_startup_state, 2
0x180001181  xor     dil, dil
0x180001184  mov     cl, bl
0x180001186  call    __scrt_release_startup_lock
0x18000118b  test    dil, dil
0x18000118e  jnz     short loc_1800011CA
0x180001190  call    __scrt_get_dyn_tls_init_callback
0x180001195  mov     rbx, rax
0x180001198  cmp     qword ptr [rax], 0
0x18000119c  jz      short loc_1800011BD
0x18000119e  mov     rcx, rax
0x1800011a1  call    __scrt_is_nonwritable_in_current_image
0x1800011a6  test    al, al
0x1800011a8  jz      short loc_1800011BD
0x1800011aa  mov     r8, rsi
0x1800011ad  mov     edx, 2
0x1800011b2  mov     rcx, r14
0x1800011b5  mov     rax, [rbx]
0x1800011b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800011bd  inc     cs:dword_18000A0D0
0x1800011c3  mov     eax, 1
0x1800011c8  jmp     short loc_1800011CC
0x1800011ca  xor     eax, eax
0x1800011cc  add     rsp, 28h
0x1800011d0  pop     r14
0x1800011d2  pop     rdi
0x1800011d3  pop     rsi
0x1800011d4  pop     rbx
0x1800011d5  retn
0x1800011d6  mov     ecx, 7
0x1800011db  call    __scrt_fastfail
0x1800064ec  push    rbp
0x1800064ee  sub     rsp, 20h
0x1800064f2  mov     rbp, rdx
0x1800064f5  mov     cl, [rbp+60h]
0x1800064f8  add     rsp, 20h
0x1800064fc  pop     rbp
0x1800064fd  jmp     __scrt_release_startup_lock
```
