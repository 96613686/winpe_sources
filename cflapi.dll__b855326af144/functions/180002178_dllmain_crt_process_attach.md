# dllmain_crt_process_attach

- ea: `0x180002178`
- end: `0x180002272`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180002120`

## callees

- `0x180002178`
- `0x1800024b4`
- `0x1800024f4`
- `0x180002530`
- `0x180002630`
- `0x180002704`
- `0x1800027a4`
- `0x1800029c8`
- `0x1800029f0`
- `0x180002a14`
- `0x180002a24`
- `0x180002a30`
- `0x180002dd6`
- `0x180002de2`
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
  ++dword_18003F570;
  return 1;
}

```

## disassembly

```asm
0x180002178  push    rbx
0x18000217a  push    rsi
0x18000217b  push    rdi
0x18000217c  push    r14
0x18000217e  sub     rsp, 28h
0x180002182  mov     rsi, rdx
0x180002185  mov     r14, rcx
0x180002188  xor     ecx, ecx
0x18000218a  call    __scrt_initialize_crt
0x18000218f  test    al, al
0x180002191  jz      loc_18000225A
0x180002197  call    __scrt_acquire_startup_lock
0x18000219c  mov     bl, al
0x18000219e  mov     [rsp+48h+arg_10], al
0x1800021a2  mov     dil, 1
0x1800021a5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800021ac  jnz     loc_180002266
0x1800021b2  mov     cs:__scrt_current_native_startup_state, 1
0x1800021bc  call    __scrt_dllmain_before_initialize_c
0x1800021c1  test    al, al
0x1800021c3  jz      short loc_180002214
0x1800021c5  call    _RTC_Initialize
0x1800021ca  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800021cf  call    __scrt_initialize_default_local_stdio_options
0x1800021d4  lea     rdx, __xi_z; Last
0x1800021db  lea     rcx, __xi_a; First
0x1800021e2  call    _initterm_e_0
0x1800021e7  test    eax, eax
0x1800021e9  jnz     short loc_180002214
0x1800021eb  call    __scrt_dllmain_after_initialize_c
0x1800021f0  test    al, al
0x1800021f2  jz      short loc_180002214
0x1800021f4  lea     rdx, __xc_z; Last
0x1800021fb  lea     rcx, __xc_a; First
0x180002202  call    _initterm_0
0x180002207  mov     cs:__scrt_current_native_startup_state, 2
0x180002211  xor     dil, dil
0x180002214  mov     cl, bl
0x180002216  call    __scrt_release_startup_lock
0x18000221b  test    dil, dil
0x18000221e  jnz     short loc_18000225A
0x180002220  call    __scrt_get_dyn_tls_init_callback
0x180002225  mov     rbx, rax
0x180002228  cmp     qword ptr [rax], 0
0x18000222c  jz      short loc_18000224D
0x18000222e  mov     rcx, rax
0x180002231  call    __scrt_is_nonwritable_in_current_image
0x180002236  test    al, al
0x180002238  jz      short loc_18000224D
0x18000223a  mov     r8, rsi
0x18000223d  mov     edx, 2
0x180002242  mov     rcx, r14
0x180002245  mov     rax, [rbx]
0x180002248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000224d  inc     cs:dword_18003F570
0x180002253  mov     eax, 1
0x180002258  jmp     short loc_18000225C
0x18000225a  xor     eax, eax
0x18000225c  add     rsp, 28h
0x180002260  pop     r14
0x180002262  pop     rdi
0x180002263  pop     rsi
0x180002264  pop     rbx
0x180002265  retn
0x180002266  mov     ecx, 7
0x18000226b  call    __scrt_fastfail
0x18002e07c  push    rbp
0x18002e07e  sub     rsp, 20h
0x18002e082  mov     rbp, rdx
0x18002e085  mov     cl, [rbp+60h]
0x18002e088  add     rsp, 20h
0x18002e08c  pop     rbp
0x18002e08d  jmp     __scrt_release_startup_lock
```
