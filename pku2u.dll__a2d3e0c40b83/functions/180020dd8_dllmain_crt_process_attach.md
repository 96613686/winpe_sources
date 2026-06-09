# dllmain_crt_process_attach

- ea: `0x180020dd8`
- end: `0x180020ed2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180020d80`

## callees

- `0x180020dd8`
- `0x1800211d0`
- `0x1800211f8`
- `0x18002121c`
- `0x18002125c`
- `0x180021298`
- `0x180021398`
- `0x18002146c`
- `0x18002150c`
- `0x1800215c8`
- `0x1800215d8`
- `0x1800215e4`
- `0x180021946`
- `0x180021952`
- `0x180046010`

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
  ++dword_180054950;
  return 1;
}

```

## disassembly

```asm
0x180020dd8  push    rbx
0x180020dda  push    rsi
0x180020ddb  push    rdi
0x180020ddc  push    r14
0x180020dde  sub     rsp, 28h
0x180020de2  mov     rsi, rdx
0x180020de5  mov     r14, rcx
0x180020de8  xor     ecx, ecx
0x180020dea  call    __scrt_initialize_crt
0x180020def  test    al, al
0x180020df1  jz      loc_180020EBA
0x180020df7  call    __scrt_acquire_startup_lock
0x180020dfc  mov     bl, al
0x180020dfe  mov     [rsp+48h+arg_10], al
0x180020e02  mov     dil, 1
0x180020e05  cmp     cs:__scrt_current_native_startup_state, 0
0x180020e0c  jnz     loc_180020EC6
0x180020e12  mov     cs:__scrt_current_native_startup_state, 1
0x180020e1c  call    __scrt_dllmain_before_initialize_c
0x180020e21  test    al, al
0x180020e23  jz      short loc_180020E74
0x180020e25  call    _RTC_Initialize
0x180020e2a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180020e2f  call    __scrt_initialize_default_local_stdio_options
0x180020e34  lea     rdx, __xi_z; Last
0x180020e3b  lea     rcx, __xi_a; First
0x180020e42  call    _initterm_e_0
0x180020e47  test    eax, eax
0x180020e49  jnz     short loc_180020E74
0x180020e4b  call    __scrt_dllmain_after_initialize_c
0x180020e50  test    al, al
0x180020e52  jz      short loc_180020E74
0x180020e54  lea     rdx, __xc_z; Last
0x180020e5b  lea     rcx, __xc_a; First
0x180020e62  call    _initterm_0
0x180020e67  mov     cs:__scrt_current_native_startup_state, 2
0x180020e71  xor     dil, dil
0x180020e74  mov     cl, bl
0x180020e76  call    __scrt_release_startup_lock
0x180020e7b  test    dil, dil
0x180020e7e  jnz     short loc_180020EBA
0x180020e80  call    __scrt_get_dyn_tls_init_callback
0x180020e85  mov     rbx, rax
0x180020e88  cmp     qword ptr [rax], 0
0x180020e8c  jz      short loc_180020EAD
0x180020e8e  mov     rcx, rax
0x180020e91  call    __scrt_is_nonwritable_in_current_image
0x180020e96  test    al, al
0x180020e98  jz      short loc_180020EAD
0x180020e9a  mov     r8, rsi
0x180020e9d  mov     edx, 2
0x180020ea2  mov     rcx, r14
0x180020ea5  mov     rax, [rbx]
0x180020ea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ead  inc     cs:dword_180054950
0x180020eb3  mov     eax, 1
0x180020eb8  jmp     short loc_180020EBC
0x180020eba  xor     eax, eax
0x180020ebc  add     rsp, 28h
0x180020ec0  pop     r14
0x180020ec2  pop     rdi
0x180020ec3  pop     rsi
0x180020ec4  pop     rbx
0x180020ec5  retn
0x180020ec6  mov     ecx, 7
0x180020ecb  call    __scrt_fastfail
0x180045056  push    rbp
0x180045058  sub     rsp, 20h
0x18004505c  mov     rbp, rdx
0x18004505f  mov     cl, [rbp+60h]
0x180045062  add     rsp, 20h
0x180045066  pop     rbp
0x180045067  jmp     __scrt_release_startup_lock
```
