# dllmain_crt_process_attach

- ea: `0x1800011f8`
- end: `0x1800012f2`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800011a0`

## callees

- `0x1800011f8`
- `0x18000159c`
- `0x1800015dc`
- `0x180001618`
- `0x180001718`
- `0x1800017ec`
- `0x18000188c`
- `0x180001a48`
- `0x180001a70`
- `0x180001a94`
- `0x180001aa4`
- `0x180001ab0`
- `0x180001fa6`
- `0x180001fb2`
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
  ++dword_18000E1F0;
  return 1;
}

```

## disassembly

```asm
0x1800011f8  push    rbx
0x1800011fa  push    rsi
0x1800011fb  push    rdi
0x1800011fc  push    r14
0x1800011fe  sub     rsp, 28h
0x180001202  mov     rsi, rdx
0x180001205  mov     r14, rcx
0x180001208  xor     ecx, ecx
0x18000120a  call    __scrt_initialize_crt
0x18000120f  test    al, al
0x180001211  jz      loc_1800012DA
0x180001217  call    __scrt_acquire_startup_lock
0x18000121c  mov     bl, al
0x18000121e  mov     [rsp+48h+arg_10], al
0x180001222  mov     dil, 1
0x180001225  cmp     cs:__scrt_current_native_startup_state, 0
0x18000122c  jnz     loc_1800012E6
0x180001232  mov     cs:__scrt_current_native_startup_state, 1
0x18000123c  call    __scrt_dllmain_before_initialize_c
0x180001241  test    al, al
0x180001243  jz      short loc_180001294
0x180001245  call    _RTC_Initialize
0x18000124a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18000124f  call    __scrt_initialize_default_local_stdio_options
0x180001254  lea     rdx, __xi_z; Last
0x18000125b  lea     rcx, __xi_a; First
0x180001262  call    _initterm_e_0
0x180001267  test    eax, eax
0x180001269  jnz     short loc_180001294
0x18000126b  call    __scrt_dllmain_after_initialize_c
0x180001270  test    al, al
0x180001272  jz      short loc_180001294
0x180001274  lea     rdx, __xc_z; Last
0x18000127b  lea     rcx, __xc_a; First
0x180001282  call    _initterm_0
0x180001287  mov     cs:__scrt_current_native_startup_state, 2
0x180001291  xor     dil, dil
0x180001294  mov     cl, bl
0x180001296  call    __scrt_release_startup_lock
0x18000129b  test    dil, dil
0x18000129e  jnz     short loc_1800012DA
0x1800012a0  call    __scrt_get_dyn_tls_init_callback
0x1800012a5  mov     rbx, rax
0x1800012a8  cmp     qword ptr [rax], 0
0x1800012ac  jz      short loc_1800012CD
0x1800012ae  mov     rcx, rax
0x1800012b1  call    __scrt_is_nonwritable_in_current_image
0x1800012b6  test    al, al
0x1800012b8  jz      short loc_1800012CD
0x1800012ba  mov     r8, rsi
0x1800012bd  mov     edx, 2
0x1800012c2  mov     rcx, r14
0x1800012c5  mov     rax, [rbx]
0x1800012c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800012cd  inc     cs:dword_18000E1F0
0x1800012d3  mov     eax, 1
0x1800012d8  jmp     short loc_1800012DC
0x1800012da  xor     eax, eax
0x1800012dc  add     rsp, 28h
0x1800012e0  pop     r14
0x1800012e2  pop     rdi
0x1800012e3  pop     rsi
0x1800012e4  pop     rbx
0x1800012e5  retn
0x1800012e6  mov     ecx, 7
0x1800012eb  call    __scrt_fastfail
0x18000814c  push    rbp
0x18000814e  sub     rsp, 20h
0x180008152  mov     rbp, rdx
0x180008155  mov     cl, [rbp+60h]
0x180008158  add     rsp, 20h
0x18000815c  pop     rbp
0x18000815d  jmp     __scrt_release_startup_lock
```
