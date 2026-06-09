# dllmain_crt_process_attach

- ea: `0x18001b4c8`
- end: `0x18001b5c2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x18001b470`

## callees

- `0x18001b4c8`
- `0x18001b8ec`
- `0x18001b914`
- `0x18001b938`
- `0x18001b978`
- `0x18001b9b4`
- `0x18001bab4`
- `0x18001bb88`
- `0x18001bc28`
- `0x18001bce4`
- `0x18001bcf4`
- `0x18001bd00`
- `0x18001c056`
- `0x18001c062`
- `0x18002f010`

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
  ++dword_18003F310;
  return 1;
}

```

## disassembly

```asm
0x18001b4c8  push    rbx
0x18001b4ca  push    rsi
0x18001b4cb  push    rdi
0x18001b4cc  push    r14
0x18001b4ce  sub     rsp, 28h
0x18001b4d2  mov     rsi, rdx
0x18001b4d5  mov     r14, rcx
0x18001b4d8  xor     ecx, ecx
0x18001b4da  call    __scrt_initialize_crt
0x18001b4df  test    al, al
0x18001b4e1  jz      loc_18001B5AA
0x18001b4e7  call    __scrt_acquire_startup_lock
0x18001b4ec  mov     bl, al
0x18001b4ee  mov     [rsp+48h+arg_10], al
0x18001b4f2  mov     dil, 1
0x18001b4f5  cmp     cs:__scrt_current_native_startup_state, 0
0x18001b4fc  jnz     loc_18001B5B6
0x18001b502  mov     cs:__scrt_current_native_startup_state, 1
0x18001b50c  call    __scrt_dllmain_before_initialize_c
0x18001b511  test    al, al
0x18001b513  jz      short loc_18001B564
0x18001b515  call    _RTC_Initialize
0x18001b51a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18001b51f  call    __scrt_initialize_default_local_stdio_options
0x18001b524  lea     rdx, __xi_z; Last
0x18001b52b  lea     rcx, __xi_a; First
0x18001b532  call    _initterm_e_0
0x18001b537  test    eax, eax
0x18001b539  jnz     short loc_18001B564
0x18001b53b  call    __scrt_dllmain_after_initialize_c
0x18001b540  test    al, al
0x18001b542  jz      short loc_18001B564
0x18001b544  lea     rdx, __xc_z; Last
0x18001b54b  lea     rcx, __xc_a; First
0x18001b552  call    _initterm_0
0x18001b557  mov     cs:__scrt_current_native_startup_state, 2
0x18001b561  xor     dil, dil
0x18001b564  mov     cl, bl
0x18001b566  call    __scrt_release_startup_lock
0x18001b56b  test    dil, dil
0x18001b56e  jnz     short loc_18001B5AA
0x18001b570  call    __scrt_get_dyn_tls_init_callback
0x18001b575  mov     rbx, rax
0x18001b578  cmp     qword ptr [rax], 0
0x18001b57c  jz      short loc_18001B59D
0x18001b57e  mov     rcx, rax
0x18001b581  call    __scrt_is_nonwritable_in_current_image
0x18001b586  test    al, al
0x18001b588  jz      short loc_18001B59D
0x18001b58a  mov     r8, rsi
0x18001b58d  mov     edx, 2
0x18001b592  mov     rcx, r14
0x18001b595  mov     rax, [rbx]
0x18001b598  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b59d  inc     cs:dword_18003F310
0x18001b5a3  mov     eax, 1
0x18001b5a8  jmp     short loc_18001B5AC
0x18001b5aa  xor     eax, eax
0x18001b5ac  add     rsp, 28h
0x18001b5b0  pop     r14
0x18001b5b2  pop     rdi
0x18001b5b3  pop     rsi
0x18001b5b4  pop     rbx
0x18001b5b5  retn
0x18001b5b6  mov     ecx, 7
0x18001b5bb  call    __scrt_fastfail
0x18002e1fc  push    rbp
0x18002e1fe  sub     rsp, 20h
0x18002e202  mov     rbp, rdx
0x18002e205  mov     cl, [rbp+60h]
0x18002e208  add     rsp, 20h
0x18002e20c  pop     rbp
0x18002e20d  jmp     __scrt_release_startup_lock
```
