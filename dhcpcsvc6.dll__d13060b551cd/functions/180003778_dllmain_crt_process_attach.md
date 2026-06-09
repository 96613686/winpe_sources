# dllmain_crt_process_attach

- ea: `0x180003778`
- end: `0x180003872`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180003720`

## callees

- `0x180003778`
- `0x180003b70`
- `0x180003b98`
- `0x180003bbc`
- `0x180003bfc`
- `0x180003c38`
- `0x180003d38`
- `0x180003e0c`
- `0x180003eac`
- `0x180003f08`
- `0x180003f18`
- `0x180003f24`
- `0x180004286`
- `0x180004292`
- `0x180009010`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_attach(__int64 a1, __int64 a2)
{
  char v4; // bl
  char v5; // di
  void (__fastcall **dyn_tls_init_callback)(__int64, __int64, __int64); // rax
  void (__fastcall **v7)(__int64, __int64, __int64); // rbx

  if ( !(unsigned __int8)_scrt_initialize_crt(0) )
    return 0;
  v4 = _scrt_acquire_startup_lock();
  v5 = 1;
  if ( _scrt_current_native_startup_state )
    _scrt_fastfail(7u);
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
  _scrt_release_startup_lock(v4);
  if ( v5 )
    return 0;
  dyn_tls_init_callback = (void (__fastcall **)(__int64, __int64, __int64))_scrt_get_dyn_tls_init_callback();
  v7 = dyn_tls_init_callback;
  if ( *dyn_tls_init_callback )
  {
    if ( (unsigned __int8)_scrt_is_nonwritable_in_current_image(dyn_tls_init_callback) )
      (*v7)(a1, 2, a2);
  }
  ++dword_18000F090;
  return 1;
}

```

## disassembly

```asm
0x180003778  push    rbx
0x18000377a  push    rsi
0x18000377b  push    rdi
0x18000377c  push    r14
0x18000377e  sub     rsp, 28h
0x180003782  mov     rsi, rdx
0x180003785  mov     r14, rcx
0x180003788  xor     ecx, ecx
0x18000378a  call    __scrt_initialize_crt
0x18000378f  test    al, al
0x180003791  jz      loc_18000385A
0x180003797  call    __scrt_acquire_startup_lock
0x18000379c  mov     bl, al
0x18000379e  mov     [rsp+48h+arg_10], al
0x1800037a2  mov     dil, 1
0x1800037a5  cmp     cs:__scrt_current_native_startup_state, 0
0x1800037ac  jnz     loc_180003866
0x1800037b2  mov     cs:__scrt_current_native_startup_state, 1
0x1800037bc  call    __scrt_dllmain_before_initialize_c
0x1800037c1  test    al, al
0x1800037c3  jz      short loc_180003814
0x1800037c5  call    _RTC_Initialize
0x1800037ca  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800037cf  call    __scrt_initialize_default_local_stdio_options
0x1800037d4  lea     rdx, __xi_z; Last
0x1800037db  lea     rcx, __xi_a; First
0x1800037e2  call    _initterm_e_0
0x1800037e7  test    eax, eax
0x1800037e9  jnz     short loc_180003814
0x1800037eb  call    __scrt_dllmain_after_initialize_c
0x1800037f0  test    al, al
0x1800037f2  jz      short loc_180003814
0x1800037f4  lea     rdx, __xc_z; Last
0x1800037fb  lea     rcx, __xc_a; First
0x180003802  call    _initterm_0
0x180003807  mov     cs:__scrt_current_native_startup_state, 2
0x180003811  xor     dil, dil
0x180003814  mov     cl, bl
0x180003816  call    __scrt_release_startup_lock
0x18000381b  test    dil, dil
0x18000381e  jnz     short loc_18000385A
0x180003820  call    __scrt_get_dyn_tls_init_callback
0x180003825  mov     rbx, rax
0x180003828  cmp     qword ptr [rax], 0
0x18000382c  jz      short loc_18000384D
0x18000382e  mov     rcx, rax
0x180003831  call    __scrt_is_nonwritable_in_current_image
0x180003836  test    al, al
0x180003838  jz      short loc_18000384D
0x18000383a  mov     r8, rsi
0x18000383d  mov     edx, 2
0x180003842  mov     rcx, r14
0x180003845  mov     rax, [rbx]
0x180003848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000384d  inc     cs:dword_18000F090
0x180003853  mov     eax, 1
0x180003858  jmp     short loc_18000385C
0x18000385a  xor     eax, eax
0x18000385c  add     rsp, 28h
0x180003860  pop     r14
0x180003862  pop     rdi
0x180003863  pop     rsi
0x180003864  pop     rbx
0x180003865  retn
0x180003866  mov     ecx, 7
0x18000386b  call    __scrt_fastfail
0x180007962  push    rbp
0x180007964  sub     rsp, 20h
0x180007968  mov     rbp, rdx
0x18000796b  mov     cl, [rbp+60h]
0x18000796e  add     rsp, 20h
0x180007972  pop     rbp
0x180007973  jmp     __scrt_release_startup_lock
```
