# dllmain_crt_process_attach

- ea: `0x18001dea8`
- end: `0x18001dfa2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x18001de50`

## callees

- `0x18001dea8`
- `0x18001e1f4`
- `0x18001e234`
- `0x18001e270`
- `0x18001e370`
- `0x18001e444`
- `0x18001e4e4`
- `0x18001e698`
- `0x18001e6c0`
- `0x18001e6e4`
- `0x18001e6f4`
- `0x18001e700`
- `0x18001ea56`
- `0x18001ea62`
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
  ++dword_18003C490;
  return 1;
}

```

## disassembly

```asm
0x18001dea8  push    rbx
0x18001deaa  push    rsi
0x18001deab  push    rdi
0x18001deac  push    r14
0x18001deae  sub     rsp, 28h
0x18001deb2  mov     rsi, rdx
0x18001deb5  mov     r14, rcx
0x18001deb8  xor     ecx, ecx
0x18001deba  call    __scrt_initialize_crt
0x18001debf  test    al, al
0x18001dec1  jz      loc_18001DF8A
0x18001dec7  call    __scrt_acquire_startup_lock
0x18001decc  mov     bl, al
0x18001dece  mov     [rsp+48h+arg_10], al
0x18001ded2  mov     dil, 1
0x18001ded5  cmp     cs:__scrt_current_native_startup_state, 0
0x18001dedc  jnz     loc_18001DF96
0x18001dee2  mov     cs:__scrt_current_native_startup_state, 1
0x18001deec  call    __scrt_dllmain_before_initialize_c
0x18001def1  test    al, al
0x18001def3  jz      short loc_18001DF44
0x18001def5  call    _RTC_Initialize
0x18001defa  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18001deff  call    __scrt_initialize_default_local_stdio_options
0x18001df04  lea     rdx, __xi_z; Last
0x18001df0b  lea     rcx, __xi_a; First
0x18001df12  call    _initterm_e_0
0x18001df17  test    eax, eax
0x18001df19  jnz     short loc_18001DF44
0x18001df1b  call    __scrt_dllmain_after_initialize_c
0x18001df20  test    al, al
0x18001df22  jz      short loc_18001DF44
0x18001df24  lea     rdx, __xc_z; Last
0x18001df2b  lea     rcx, __xc_a; First
0x18001df32  call    _initterm_0
0x18001df37  mov     cs:__scrt_current_native_startup_state, 2
0x18001df41  xor     dil, dil
0x18001df44  mov     cl, bl
0x18001df46  call    __scrt_release_startup_lock
0x18001df4b  test    dil, dil
0x18001df4e  jnz     short loc_18001DF8A
0x18001df50  call    __scrt_get_dyn_tls_init_callback
0x18001df55  mov     rbx, rax
0x18001df58  cmp     qword ptr [rax], 0
0x18001df5c  jz      short loc_18001DF7D
0x18001df5e  mov     rcx, rax
0x18001df61  call    __scrt_is_nonwritable_in_current_image
0x18001df66  test    al, al
0x18001df68  jz      short loc_18001DF7D
0x18001df6a  mov     r8, rsi
0x18001df6d  mov     edx, 2
0x18001df72  mov     rcx, r14
0x18001df75  mov     rax, [rbx]
0x18001df78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df7d  inc     cs:dword_18003C490
0x18001df83  mov     eax, 1
0x18001df88  jmp     short loc_18001DF8C
0x18001df8a  xor     eax, eax
0x18001df8c  add     rsp, 28h
0x18001df90  pop     r14
0x18001df92  pop     rdi
0x18001df93  pop     rsi
0x18001df94  pop     rbx
0x18001df95  retn
0x18001df96  mov     ecx, 7
0x18001df9b  call    __scrt_fastfail
0x18002f700  push    rbp
0x18002f702  sub     rsp, 20h
0x18002f706  mov     rbp, rdx
0x18002f709  mov     cl, [rbp+60h]
0x18002f70c  add     rsp, 20h
0x18002f710  pop     rbp
0x18002f711  jmp     __scrt_release_startup_lock
```
