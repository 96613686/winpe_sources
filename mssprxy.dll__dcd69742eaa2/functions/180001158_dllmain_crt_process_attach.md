# dllmain_crt_process_attach

- ea: `0x180001158`
- end: `0x180001252`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x180001100`

## callees

- `0x180001158`
- `0x180001550`
- `0x180001578`
- `0x18000159c`
- `0x1800015dc`
- `0x180001618`
- `0x180001718`
- `0x1800017ec`
- `0x18000188c`
- `0x1800018e8`
- `0x1800018f8`
- `0x180001904`
- `0x180001c76`
- `0x180001c82`
- `0x180003010`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_attach(__int64 a1, __int64 a2)
{
  char v4; // bl
  char v5; // di
  __int64 *dyn_tls_init_callback; // rax
  __int64 *v7; // rbx

  if ( !_scrt_initialize_crt(0) )
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
  dyn_tls_init_callback = _scrt_get_dyn_tls_init_callback();
  v7 = dyn_tls_init_callback;
  if ( *dyn_tls_init_callback )
  {
    if ( _scrt_is_nonwritable_in_current_image((__int64)dyn_tls_init_callback) )
      ((void (__fastcall *)(__int64, __int64, __int64))*v7)(a1, 2, a2);
  }
  ++dword_18002A090;
  return 1;
}

```

## disassembly

```asm
0x180001158  push    rbx
0x18000115a  push    rsi
0x18000115b  push    rdi
0x18000115c  push    r14
0x18000115e  sub     rsp, 28h
0x180001162  mov     rsi, rdx
0x180001165  mov     r14, rcx
0x180001168  xor     ecx, ecx
0x18000116a  call    __scrt_initialize_crt
0x18000116f  test    al, al
0x180001171  jz      loc_18000123A
0x180001177  call    __scrt_acquire_startup_lock
0x18000117c  mov     bl, al
0x18000117e  mov     [rsp+48h+arg_10], al
0x180001182  mov     dil, 1
0x180001185  cmp     cs:__scrt_current_native_startup_state, 0
0x18000118c  jnz     loc_180001246
0x180001192  mov     cs:__scrt_current_native_startup_state, 1
0x18000119c  call    __scrt_dllmain_before_initialize_c
0x1800011a1  test    al, al
0x1800011a3  jz      short loc_1800011F4
0x1800011a5  call    _RTC_Initialize
0x1800011aa  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x1800011af  call    __scrt_initialize_default_local_stdio_options
0x1800011b4  lea     rdx, __xi_z; Last
0x1800011bb  lea     rcx, __xi_a; First
0x1800011c2  call    _initterm_e_0
0x1800011c7  test    eax, eax
0x1800011c9  jnz     short loc_1800011F4
0x1800011cb  call    __scrt_dllmain_after_initialize_c
0x1800011d0  test    al, al
0x1800011d2  jz      short loc_1800011F4
0x1800011d4  lea     rdx, __xc_z; Last
0x1800011db  lea     rcx, __xc_a; First
0x1800011e2  call    _initterm_0
0x1800011e7  mov     cs:__scrt_current_native_startup_state, 2
0x1800011f1  xor     dil, dil
0x1800011f4  mov     cl, bl
0x1800011f6  call    __scrt_release_startup_lock
0x1800011fb  test    dil, dil
0x1800011fe  jnz     short loc_18000123A
0x180001200  call    __scrt_get_dyn_tls_init_callback
0x180001205  mov     rbx, rax
0x180001208  cmp     qword ptr [rax], 0
0x18000120c  jz      short loc_18000122D
0x18000120e  mov     rcx, rax
0x180001211  call    __scrt_is_nonwritable_in_current_image
0x180001216  test    al, al
0x180001218  jz      short loc_18000122D
0x18000121a  mov     r8, rsi
0x18000121d  mov     edx, 2
0x180001222  mov     rcx, r14
0x180001225  mov     rax, [rbx]
0x180001228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000122d  inc     cs:dword_18002A090
0x180001233  mov     eax, 1
0x180001238  jmp     short loc_18000123C
0x18000123a  xor     eax, eax
0x18000123c  add     rsp, 28h
0x180001240  pop     r14
0x180001242  pop     rdi
0x180001243  pop     rsi
0x180001244  pop     rbx
0x180001245  retn
0x180001246  mov     ecx, 7
0x18000124b  call    __scrt_fastfail
0x18000230c  push    rbp
0x18000230e  sub     rsp, 20h
0x180002312  mov     rbp, rdx
0x180002315  mov     cl, [rbp+60h]
0x180002318  add     rsp, 20h
0x18000231c  pop     rbp
0x18000231d  jmp     __scrt_release_startup_lock
```
