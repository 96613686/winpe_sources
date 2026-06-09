# dllmain_crt_process_attach

- ea: `0x180001788`
- end: `0x180001882`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001730`

## callees

- `0x180001788`
- `0x180001b80`
- `0x180001ba8`
- `0x180001bcc`
- `0x180001c0c`
- `0x180001c48`
- `0x180001d48`
- `0x180001e1c`
- `0x180001ebc`
- `0x180001f18`
- `0x180001f28`
- `0x180001f34`
- `0x1800022a6`
- `0x1800022b2`
- `0x18001e010`

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
  ++dword_18002A810;
  return 1;
}

```

## disassembly

```asm
0x180001788  push    rbx
0x18000178a  push    rsi
0x18000178b  push    rdi
0x18000178c  push    r14
0x18000178e  sub     rsp, 28h
0x180001792  mov     rsi, rdx
0x180001795  mov     r14, rcx
0x180001798  xor     ecx, ecx
0x18000179a  call    __scrt_initialize_crt
0x18000179f  test    al, al
0x1800017a1  jz      loc_18000186A
0x1800017a7  call    __scrt_acquire_startup_lock
0x1800017ac  mov     bl, al
0x1800017ae  mov     [rsp+48h+arg_10], al
0x1800017b2  mov     dil, 1
0x1800017b5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800017bc  jnz     loc_180001876
0x1800017c2  mov     cs:__scrt_current_native_startup_state, 1
0x1800017cc  call    __scrt_dllmain_before_initialize_c
0x1800017d1  test    al, al
0x1800017d3  jz      short loc_180001824
0x1800017d5  call    _RTC_Initialize
0x1800017da  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800017df  call    __scrt_initialize_default_local_stdio_options
0x1800017e4  lea     rdx, __xi_z; Last
0x1800017eb  lea     rcx, __xi_a; First
0x1800017f2  call    _initterm_e_0
0x1800017f7  test    eax, eax
0x1800017f9  jnz     short loc_180001824
0x1800017fb  call    __scrt_dllmain_after_initialize_c
0x180001800  test    al, al
0x180001802  jz      short loc_180001824
0x180001804  lea     rdx, __xc_z; Last
0x18000180b  lea     rcx, __xc_a; First
0x180001812  call    _initterm_0
0x180001817  mov     cs:__scrt_current_native_startup_state, 2
0x180001821  xor     dil, dil
0x180001824  mov     cl, bl
0x180001826  call    __scrt_release_startup_lock
0x18000182b  test    dil, dil
0x18000182e  jnz     short loc_18000186A
0x180001830  call    __scrt_get_dyn_tls_init_callback
0x180001835  mov     rbx, rax
0x180001838  cmp     qword ptr [rax], 0
0x18000183c  jz      short loc_18000185D
0x18000183e  mov     rcx, rax
0x180001841  call    __scrt_is_nonwritable_in_current_image
0x180001846  test    al, al
0x180001848  jz      short loc_18000185D
0x18000184a  mov     r8, rsi
0x18000184d  mov     edx, 2
0x180001852  mov     rcx, r14
0x180001855  mov     rax, [rbx]
0x180001858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000185d  inc     cs:dword_18002A810
0x180001863  mov     eax, 1
0x180001868  jmp     short loc_18000186C
0x18000186a  xor     eax, eax
0x18000186c  add     rsp, 28h
0x180001870  pop     r14
0x180001872  pop     rdi
0x180001873  pop     rsi
0x180001874  pop     rbx
0x180001875  retn
0x180001876  mov     ecx, 7
0x18000187b  call    __scrt_fastfail
0x18001d12c  push    rbp
0x18001d12e  sub     rsp, 20h
0x18001d132  mov     rbp, rdx
0x18001d135  mov     cl, [rbp+60h]
0x18001d138  add     rsp, 20h
0x18001d13c  pop     rbp
0x18001d13d  jmp     __scrt_release_startup_lock
```
