# dllmain_crt_process_attach

- ea: `0x180002308`
- end: `0x180002402`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800022b0`

## callees

- `0x180002308`
- `0x180002650`
- `0x180002690`
- `0x1800026cc`
- `0x1800027cc`
- `0x1800028a0`
- `0x180002940`
- `0x180002adc`
- `0x180002b04`
- `0x180002b28`
- `0x180002b38`
- `0x180002b44`
- `0x180002e86`
- `0x180002e92`
- `0x180013010`

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
  ++dword_18001A210;
  return 1;
}

```

## disassembly

```asm
0x180002308  push    rbx
0x18000230a  push    rsi
0x18000230b  push    rdi
0x18000230c  push    r14
0x18000230e  sub     rsp, 28h
0x180002312  mov     rsi, rdx
0x180002315  mov     r14, rcx
0x180002318  xor     ecx, ecx
0x18000231a  call    __scrt_initialize_crt
0x18000231f  test    al, al
0x180002321  jz      loc_1800023EA
0x180002327  call    __scrt_acquire_startup_lock
0x18000232c  mov     bl, al
0x18000232e  mov     [rsp+48h+arg_10], al
0x180002332  mov     dil, 1
0x180002335  cmp     cs:__scrt_current_native_startup_state, 0
0x18000233c  jnz     loc_1800023F6
0x180002342  mov     cs:__scrt_current_native_startup_state, 1
0x18000234c  call    __scrt_dllmain_before_initialize_c
0x180002351  test    al, al
0x180002353  jz      short loc_1800023A4
0x180002355  call    _RTC_Initialize
0x18000235a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000235f  call    __scrt_initialize_default_local_stdio_options
0x180002364  lea     rdx, __xi_z; Last
0x18000236b  lea     rcx, __xi_a; First
0x180002372  call    _initterm_e_0
0x180002377  test    eax, eax
0x180002379  jnz     short loc_1800023A4
0x18000237b  call    __scrt_dllmain_after_initialize_c
0x180002380  test    al, al
0x180002382  jz      short loc_1800023A4
0x180002384  lea     rdx, __xc_z; Last
0x18000238b  lea     rcx, __xc_a; First
0x180002392  call    _initterm_0
0x180002397  mov     cs:__scrt_current_native_startup_state, 2
0x1800023a1  xor     dil, dil
0x1800023a4  mov     cl, bl
0x1800023a6  call    __scrt_release_startup_lock
0x1800023ab  test    dil, dil
0x1800023ae  jnz     short loc_1800023EA
0x1800023b0  call    __scrt_get_dyn_tls_init_callback
0x1800023b5  mov     rbx, rax
0x1800023b8  cmp     qword ptr [rax], 0
0x1800023bc  jz      short loc_1800023DD
0x1800023be  mov     rcx, rax
0x1800023c1  call    __scrt_is_nonwritable_in_current_image
0x1800023c6  test    al, al
0x1800023c8  jz      short loc_1800023DD
0x1800023ca  mov     r8, rsi
0x1800023cd  mov     edx, 2
0x1800023d2  mov     rcx, r14
0x1800023d5  mov     rax, [rbx]
0x1800023d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800023dd  inc     cs:dword_18001A210
0x1800023e3  mov     eax, 1
0x1800023e8  jmp     short loc_1800023EC
0x1800023ea  xor     eax, eax
0x1800023ec  add     rsp, 28h
0x1800023f0  pop     r14
0x1800023f2  pop     rdi
0x1800023f3  pop     rsi
0x1800023f4  pop     rbx
0x1800023f5  retn
0x1800023f6  mov     ecx, 7
0x1800023fb  call    __scrt_fastfail
0x180012b0c  push    rbp
0x180012b0e  sub     rsp, 20h
0x180012b12  mov     rbp, rdx
0x180012b15  mov     cl, [rbp+60h]
0x180012b18  add     rsp, 20h
0x180012b1c  pop     rbp
0x180012b1d  jmp     __scrt_release_startup_lock
```
