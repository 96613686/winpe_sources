# dllmain_crt_process_attach

- ea: `0x180001738`
- end: `0x180001832`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800016e0`

## callees

- `0x180001738`
- `0x180001a80`
- `0x180001ac0`
- `0x180001afc`
- `0x180001bfc`
- `0x180001cd0`
- `0x180001d70`
- `0x180001f64`
- `0x180001f8c`
- `0x180001fb0`
- `0x180001fc0`
- `0x180001fcc`
- `0x1800023c6`
- `0x1800023d2`
- `0x180012010`

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
  ++dword_180019610;
  return 1;
}

```

## disassembly

```asm
0x180001738  push    rbx
0x18000173a  push    rsi
0x18000173b  push    rdi
0x18000173c  push    r14
0x18000173e  sub     rsp, 28h
0x180001742  mov     rsi, rdx
0x180001745  mov     r14, rcx
0x180001748  xor     ecx, ecx
0x18000174a  call    __scrt_initialize_crt
0x18000174f  test    al, al
0x180001751  jz      loc_18000181A
0x180001757  call    __scrt_acquire_startup_lock
0x18000175c  mov     bl, al
0x18000175e  mov     [rsp+48h+arg_10], al
0x180001762  mov     dil, 1
0x180001765  cmp     cs:__scrt_current_native_startup_state, 0
0x18000176c  jnz     loc_180001826
0x180001772  mov     cs:__scrt_current_native_startup_state, 1
0x18000177c  call    __scrt_dllmain_before_initialize_c
0x180001781  test    al, al
0x180001783  jz      short loc_1800017D4
0x180001785  call    _RTC_Initialize
0x18000178a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000178f  call    __scrt_initialize_default_local_stdio_options
0x180001794  lea     rdx, __xi_z; Last
0x18000179b  lea     rcx, __xi_a; First
0x1800017a2  call    _initterm_e_0
0x1800017a7  test    eax, eax
0x1800017a9  jnz     short loc_1800017D4
0x1800017ab  call    __scrt_dllmain_after_initialize_c
0x1800017b0  test    al, al
0x1800017b2  jz      short loc_1800017D4
0x1800017b4  lea     rdx, __xc_z; Last
0x1800017bb  lea     rcx, __xc_a; First
0x1800017c2  call    _initterm_0
0x1800017c7  mov     cs:__scrt_current_native_startup_state, 2
0x1800017d1  xor     dil, dil
0x1800017d4  mov     cl, bl
0x1800017d6  call    __scrt_release_startup_lock
0x1800017db  test    dil, dil
0x1800017de  jnz     short loc_18000181A
0x1800017e0  call    __scrt_get_dyn_tls_init_callback
0x1800017e5  mov     rbx, rax
0x1800017e8  cmp     qword ptr [rax], 0
0x1800017ec  jz      short loc_18000180D
0x1800017ee  mov     rcx, rax
0x1800017f1  call    __scrt_is_nonwritable_in_current_image
0x1800017f6  test    al, al
0x1800017f8  jz      short loc_18000180D
0x1800017fa  mov     r8, rsi
0x1800017fd  mov     edx, 2
0x180001802  mov     rcx, r14
0x180001805  mov     rax, [rbx]
0x180001808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000180d  inc     cs:dword_180019610
0x180001813  mov     eax, 1
0x180001818  jmp     short loc_18000181C
0x18000181a  xor     eax, eax
0x18000181c  add     rsp, 28h
0x180001820  pop     r14
0x180001822  pop     rdi
0x180001823  pop     rsi
0x180001824  pop     rbx
0x180001825  retn
0x180001826  mov     ecx, 7
0x18000182b  call    __scrt_fastfail
0x1800107fc  push    rbp
0x1800107fe  sub     rsp, 20h
0x180010802  mov     rbp, rdx
0x180010805  mov     cl, [rbp+60h]
0x180010808  add     rsp, 20h
0x18001080c  pop     rbp
0x18001080d  jmp     __scrt_release_startup_lock
```
