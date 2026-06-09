# dllmain_crt_process_attach

- ea: `0x180003fe8`
- end: `0x1800040e2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180003f90`

## callees

- `0x180003fe8`
- `0x180004378`
- `0x1800043b8`
- `0x1800043f4`
- `0x1800044f4`
- `0x1800045c8`
- `0x180004668`
- `0x180004818`
- `0x180004840`
- `0x180004864`
- `0x180004874`
- `0x180004880`
- `0x180004c36`
- `0x180004c42`
- `0x18000c010`

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
  ++dword_1800122D0;
  return 1;
}

```

## disassembly

```asm
0x180003fe8  push    rbx
0x180003fea  push    rsi
0x180003feb  push    rdi
0x180003fec  push    r14
0x180003fee  sub     rsp, 28h
0x180003ff2  mov     rsi, rdx
0x180003ff5  mov     r14, rcx
0x180003ff8  xor     ecx, ecx
0x180003ffa  call    __scrt_initialize_crt
0x180003fff  test    al, al
0x180004001  jz      loc_1800040CA
0x180004007  call    __scrt_acquire_startup_lock
0x18000400c  mov     bl, al
0x18000400e  mov     [rsp+48h+arg_10], al
0x180004012  mov     dil, 1
0x180004015  cmp     cs:__scrt_current_native_startup_state, 0
0x18000401c  jnz     loc_1800040D6
0x180004022  mov     cs:__scrt_current_native_startup_state, 1
0x18000402c  call    __scrt_dllmain_before_initialize_c
0x180004031  test    al, al
0x180004033  jz      short loc_180004084
0x180004035  call    _RTC_Initialize
0x18000403a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000403f  call    __scrt_initialize_default_local_stdio_options
0x180004044  lea     rdx, __xi_z; Last
0x18000404b  lea     rcx, __xi_a; First
0x180004052  call    _initterm_e_0
0x180004057  test    eax, eax
0x180004059  jnz     short loc_180004084
0x18000405b  call    __scrt_dllmain_after_initialize_c
0x180004060  test    al, al
0x180004062  jz      short loc_180004084
0x180004064  lea     rdx, __xc_z; Last
0x18000406b  lea     rcx, __xc_a; First
0x180004072  call    _initterm_0
0x180004077  mov     cs:__scrt_current_native_startup_state, 2
0x180004081  xor     dil, dil
0x180004084  mov     cl, bl
0x180004086  call    __scrt_release_startup_lock
0x18000408b  test    dil, dil
0x18000408e  jnz     short loc_1800040CA
0x180004090  call    __scrt_get_dyn_tls_init_callback
0x180004095  mov     rbx, rax
0x180004098  cmp     qword ptr [rax], 0
0x18000409c  jz      short loc_1800040BD
0x18000409e  mov     rcx, rax
0x1800040a1  call    __scrt_is_nonwritable_in_current_image
0x1800040a6  test    al, al
0x1800040a8  jz      short loc_1800040BD
0x1800040aa  mov     r8, rsi
0x1800040ad  mov     edx, 2
0x1800040b2  mov     rcx, r14
0x1800040b5  mov     rax, [rbx]
0x1800040b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040bd  inc     cs:dword_1800122D0
0x1800040c3  mov     eax, 1
0x1800040c8  jmp     short loc_1800040CC
0x1800040ca  xor     eax, eax
0x1800040cc  add     rsp, 28h
0x1800040d0  pop     r14
0x1800040d2  pop     rdi
0x1800040d3  pop     rsi
0x1800040d4  pop     rbx
0x1800040d5  retn
0x1800040d6  mov     ecx, 7
0x1800040db  call    __scrt_fastfail
0x18000b488  push    rbp
0x18000b48a  sub     rsp, 20h
0x18000b48e  mov     rbp, rdx
0x18000b491  mov     cl, [rbp+60h]
0x18000b494  add     rsp, 20h
0x18000b498  pop     rbp
0x18000b499  jmp     __scrt_release_startup_lock
```
