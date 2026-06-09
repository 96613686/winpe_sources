# dllmain_crt_process_attach

- ea: `0x180008f58`
- end: `0x180009052`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180008f00`

## callees

- `0x180008f58`
- `0x18000936c`
- `0x180009394`
- `0x1800093b8`
- `0x1800093f8`
- `0x180009434`
- `0x180009534`
- `0x180009608`
- `0x1800096a8`
- `0x180009704`
- `0x180009714`
- `0x180009720`
- `0x180009a76`
- `0x180009a82`
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
  ++dword_18001A130;
  return 1;
}

```

## disassembly

```asm
0x180008f58  push    rbx
0x180008f5a  push    rsi
0x180008f5b  push    rdi
0x180008f5c  push    r14
0x180008f5e  sub     rsp, 28h
0x180008f62  mov     rsi, rdx
0x180008f65  mov     r14, rcx
0x180008f68  xor     ecx, ecx
0x180008f6a  call    __scrt_initialize_crt
0x180008f6f  test    al, al
0x180008f71  jz      loc_18000903A
0x180008f77  call    __scrt_acquire_startup_lock
0x180008f7c  mov     bl, al
0x180008f7e  mov     [rsp+48h+arg_10], al
0x180008f82  mov     dil, 1
0x180008f85  cmp     cs:__scrt_current_native_startup_state, 0
0x180008f8c  jnz     loc_180009046
0x180008f92  mov     cs:__scrt_current_native_startup_state, 1
0x180008f9c  call    __scrt_dllmain_before_initialize_c
0x180008fa1  test    al, al
0x180008fa3  jz      short loc_180008FF4
0x180008fa5  call    _RTC_Initialize
0x180008faa  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x180008faf  call    __scrt_initialize_default_local_stdio_options
0x180008fb4  lea     rdx, __xi_z; Last
0x180008fbb  lea     rcx, __xi_a; First
0x180008fc2  call    _initterm_e_0
0x180008fc7  test    eax, eax
0x180008fc9  jnz     short loc_180008FF4
0x180008fcb  call    __scrt_dllmain_after_initialize_c
0x180008fd0  test    al, al
0x180008fd2  jz      short loc_180008FF4
0x180008fd4  lea     rdx, __xc_z; Last
0x180008fdb  lea     rcx, __xc_a; First
0x180008fe2  call    _initterm_0
0x180008fe7  mov     cs:__scrt_current_native_startup_state, 2
0x180008ff1  xor     dil, dil
0x180008ff4  mov     cl, bl
0x180008ff6  call    __scrt_release_startup_lock
0x180008ffb  test    dil, dil
0x180008ffe  jnz     short loc_18000903A
0x180009000  call    __scrt_get_dyn_tls_init_callback
0x180009005  mov     rbx, rax
0x180009008  cmp     qword ptr [rax], 0
0x18000900c  jz      short loc_18000902D
0x18000900e  mov     rcx, rax
0x180009011  call    __scrt_is_nonwritable_in_current_image
0x180009016  test    al, al
0x180009018  jz      short loc_18000902D
0x18000901a  mov     r8, rsi
0x18000901d  mov     edx, 2
0x180009022  mov     rcx, r14
0x180009025  mov     rax, [rbx]
0x180009028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000902d  inc     cs:dword_18001A130
0x180009033  mov     eax, 1
0x180009038  jmp     short loc_18000903C
0x18000903a  xor     eax, eax
0x18000903c  add     rsp, 28h
0x180009040  pop     r14
0x180009042  pop     rdi
0x180009043  pop     rsi
0x180009044  pop     rbx
0x180009045  retn
0x180009046  mov     ecx, 7
0x18000904b  call    __scrt_fastfail
0x18001272c  push    rbp
0x18001272e  sub     rsp, 20h
0x180012732  mov     rbp, rdx
0x180012735  mov     cl, [rbp+60h]
0x180012738  add     rsp, 20h
0x18001273c  pop     rbp
0x18001273d  jmp     __scrt_release_startup_lock
```
