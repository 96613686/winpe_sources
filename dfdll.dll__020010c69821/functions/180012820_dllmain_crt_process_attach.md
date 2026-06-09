# dllmain_crt_process_attach

- ea: `0x180012820`
- end: `0x180012936`
- name: `dllmain_crt_process_attach`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, installer_update`

## callers

- `0x1800127d0`

## callees

- `0x180012820`
- `0x180012c90`
- `0x180012ccc`
- `0x180012d00`
- `0x180012dfc`
- `0x180012ed4`
- `0x180012f6c`
- `0x1800130bc`
- `0x1800130e8`
- `0x180013104`
- `0x180013114`
- `0x180013260`
- `0x1800172f0`
- `0x180017368`
- `0x18001efd0`

## pseudocode

```c
__int64 dllmain_crt_process_attach()
{
  char v0; // bl
  char v1; // di
  __int64 v2; // rcx
  _QWORD *dyn_tls_init_callback; // rax

  if ( !(unsigned __int8)_scrt_initialize_crt(0) )
    return 0;
  v0 = _scrt_acquire_startup_lock();
  v1 = 1;
  if ( _scrt_current_native_startup_state )
  {
    _scrt_fastfail(7);
    __debugbreak();
    JUMPOUT(0x180012936LL);
  }
  _scrt_current_native_startup_state = 1;
  if ( (unsigned __int8)_scrt_dllmain_before_initialize_c() )
  {
    RTC_Initialize();
    __scrt_initialize_type_info();
    _scrt_initialize_default_local_stdio_options();
    if ( !initterm_e((_PIFV *)&_xi_a, (_PIFV *)&_xi_z) )
    {
      if ( (unsigned __int8)_scrt_dllmain_after_initialize_c() )
      {
        initterm((_PVFV *)&_xc_a, (_PVFV *)&_xc_z);
        _scrt_current_native_startup_state = 2;
        v1 = 0;
      }
    }
  }
  LOBYTE(v2) = v0;
  _scrt_release_startup_lock(v2);
  if ( v1 )
    return 0;
  dyn_tls_init_callback = (_QWORD *)_scrt_get_dyn_tls_init_callback();
  if ( *dyn_tls_init_callback )
  {
    if ( (unsigned __int8)_scrt_is_nonwritable_in_current_image(dyn_tls_init_callback) )
      _guard_dispatch_icall_fptr();
  }
  ++dword_18002DA1C;
  return 1;
}

```

## disassembly

```asm
0x180012820  mov     [rsp+arg_0], rbx
0x180012825  mov     [rsp+arg_8], rsi
0x18001282a  mov     [rsp+arg_18], rdi
0x18001282f  push    r14
0x180012831  sub     rsp, 20h
0x180012835  mov     rsi, rdx
0x180012838  mov     r14, rcx
0x18001283b  xor     ecx, ecx
0x18001283d  call    __scrt_initialize_crt
0x180012842  test    al, al
0x180012844  jz      loc_180012912
0x18001284a  call    __scrt_acquire_startup_lock
0x18001284f  mov     bl, al
0x180012851  mov     [rsp+28h+arg_10], al
0x180012855  mov     dil, 1
0x180012858  cmp     cs:__scrt_current_native_startup_state, 0
0x18001285f  jnz     loc_18001292A
0x180012865  mov     cs:__scrt_current_native_startup_state, 1
0x18001286f  call    __scrt_dllmain_before_initialize_c
0x180012874  test    al, al
0x180012876  jz      short loc_1800128C7
0x180012878  call    _RTC_Initialize
0x18001287d  call    ?__scrt_initialize_type_info@@YAXXZ
0x180012882  call    __scrt_initialize_default_local_stdio_options
0x180012887  lea     rdx, __xi_z; Last
0x18001288e  lea     rcx, __xi_a; First
0x180012895  call    _initterm_e
0x18001289a  test    eax, eax
0x18001289c  jnz     short loc_1800128C7
0x18001289e  call    __scrt_dllmain_after_initialize_c
0x1800128a3  test    al, al
0x1800128a5  jz      short loc_1800128C7
0x1800128a7  lea     rdx, __xc_z; Last
0x1800128ae  lea     rcx, __xc_a; First
0x1800128b5  call    _initterm
0x1800128ba  mov     cs:__scrt_current_native_startup_state, 2
0x1800128c4  xor     dil, dil
0x1800128c7  mov     cl, bl
0x1800128c9  call    __scrt_release_startup_lock
0x1800128ce  test    dil, dil
0x1800128d1  jnz     short loc_180012912
0x1800128d3  call    __scrt_get_dyn_tls_init_callback
0x1800128d8  mov     rbx, rax
0x1800128db  cmp     qword ptr [rax], 0
0x1800128df  jz      short loc_180012905
0x1800128e1  mov     rcx, rax
0x1800128e4  call    __scrt_is_nonwritable_in_current_image
0x1800128e9  test    al, al
0x1800128eb  jz      short loc_180012905
0x1800128ed  mov     r8, rsi
0x1800128f0  mov     edx, 2
0x1800128f5  mov     rcx, r14
0x1800128f8  mov     rax, [rbx]
0x1800128fb  mov     r9, cs:__guard_dispatch_icall_fptr
0x180012902  call    r9 ; _guard_dispatch_icall_nop
0x180012905  inc     cs:dword_18002DA1C
0x18001290b  mov     eax, 1
0x180012910  jmp     short loc_180012914
0x180012912  xor     eax, eax
0x180012914  mov     rbx, [rsp+28h+arg_0]
0x180012919  mov     rsi, [rsp+28h+arg_8]
0x18001291e  mov     rdi, [rsp+28h+arg_18]
0x180012923  add     rsp, 20h
0x180012927  pop     r14
0x180012929  retn
0x18001292a  mov     ecx, 7
0x18001292f  call    __scrt_fastfail
0x180012934  nop
0x180012935  int     3; Trap to Debugger
0x18001f43a  push    rbp
0x18001f43c  sub     rsp, 20h
0x18001f440  mov     rbp, rdx
0x18001f443  mov     cl, [rbp+40h]
0x18001f446  add     rsp, 20h
0x18001f44a  pop     rbp
0x18001f44b  jmp     __scrt_release_startup_lock
```
