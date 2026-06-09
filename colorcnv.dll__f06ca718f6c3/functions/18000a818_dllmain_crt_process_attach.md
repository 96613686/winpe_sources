# dllmain_crt_process_attach

- ea: `0x18000a818`
- end: `0x18000a912`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x18000a7c0`

## callees

- `0x18000a818`
- `0x18000ab54`
- `0x18000ab94`
- `0x18000abd0`
- `0x18000acd0`
- `0x18000ada4`
- `0x18000ae44`
- `0x18000afbc`
- `0x18000afe4`
- `0x18000b008`
- `0x18000b018`
- `0x18000b024`
- `0x18000b386`
- `0x18000b392`
- `0x18002b010`

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
  ++dword_1800338D0;
  return 1;
}

```

## disassembly

```asm
0x18000a818  push    rbx
0x18000a81a  push    rsi
0x18000a81b  push    rdi
0x18000a81c  push    r14
0x18000a81e  sub     rsp, 28h
0x18000a822  mov     rsi, rdx
0x18000a825  mov     r14, rcx
0x18000a828  xor     ecx, ecx
0x18000a82a  call    __scrt_initialize_crt
0x18000a82f  test    al, al
0x18000a831  jz      loc_18000A8FA
0x18000a837  call    __scrt_acquire_startup_lock
0x18000a83c  mov     bl, al
0x18000a83e  mov     [rsp+48h+arg_10], al
0x18000a842  mov     dil, 1
0x18000a845  cmp     cs:__scrt_current_native_startup_state, 0
0x18000a84c  jnz     loc_18000A906
0x18000a852  mov     cs:__scrt_current_native_startup_state, 1
0x18000a85c  call    __scrt_dllmain_before_initialize_c
0x18000a861  test    al, al
0x18000a863  jz      short loc_18000A8B4
0x18000a865  call    _RTC_Initialize
0x18000a86a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000a86f  call    __scrt_initialize_default_local_stdio_options
0x18000a874  lea     rdx, __xi_z; Last
0x18000a87b  lea     rcx, __xi_a; First
0x18000a882  call    _initterm_e_0
0x18000a887  test    eax, eax
0x18000a889  jnz     short loc_18000A8B4
0x18000a88b  call    __scrt_dllmain_after_initialize_c
0x18000a890  test    al, al
0x18000a892  jz      short loc_18000A8B4
0x18000a894  lea     rdx, __xc_z; Last
0x18000a89b  lea     rcx, __xc_a; First
0x18000a8a2  call    _initterm_0
0x18000a8a7  mov     cs:__scrt_current_native_startup_state, 2
0x18000a8b1  xor     dil, dil
0x18000a8b4  mov     cl, bl
0x18000a8b6  call    __scrt_release_startup_lock
0x18000a8bb  test    dil, dil
0x18000a8be  jnz     short loc_18000A8FA
0x18000a8c0  call    __scrt_get_dyn_tls_init_callback
0x18000a8c5  mov     rbx, rax
0x18000a8c8  cmp     qword ptr [rax], 0
0x18000a8cc  jz      short loc_18000A8ED
0x18000a8ce  mov     rcx, rax
0x18000a8d1  call    __scrt_is_nonwritable_in_current_image
0x18000a8d6  test    al, al
0x18000a8d8  jz      short loc_18000A8ED
0x18000a8da  mov     r8, rsi
0x18000a8dd  mov     edx, 2
0x18000a8e2  mov     rcx, r14
0x18000a8e5  mov     rax, [rbx]
0x18000a8e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8ed  inc     cs:dword_1800338D0
0x18000a8f3  mov     eax, 1
0x18000a8f8  jmp     short loc_18000A8FC
0x18000a8fa  xor     eax, eax
0x18000a8fc  add     rsp, 28h
0x18000a900  pop     r14
0x18000a902  pop     rdi
0x18000a903  pop     rsi
0x18000a904  pop     rbx
0x18000a905  retn
0x18000a906  mov     ecx, 7
0x18000a90b  call    __scrt_fastfail
0x18002a03c  push    rbp
0x18002a03e  sub     rsp, 20h
0x18002a042  mov     rbp, rdx
0x18002a045  mov     cl, [rbp+60h]
0x18002a048  add     rsp, 20h
0x18002a04c  pop     rbp
0x18002a04d  jmp     __scrt_release_startup_lock
```
