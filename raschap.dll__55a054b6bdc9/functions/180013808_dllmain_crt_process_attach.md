# dllmain_crt_process_attach

- ea: `0x180013808`
- end: `0x180013902`
- name: `dllmain_crt_process_attach`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x1800137b0`

## callees

- `0x180013808`
- `0x180013bdc`
- `0x180013c1c`
- `0x180013c58`
- `0x180013d58`
- `0x180013e2c`
- `0x180013ecc`
- `0x180014088`
- `0x1800140b0`
- `0x1800140d4`
- `0x1800140e4`
- `0x1800140f0`
- `0x1800144b6`
- `0x1800144c2`
- `0x180027010`

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
  ++dword_1800335D0;
  return 1;
}

```

## disassembly

```asm
0x180013808  push    rbx
0x18001380a  push    rsi
0x18001380b  push    rdi
0x18001380c  push    r14
0x18001380e  sub     rsp, 28h
0x180013812  mov     rsi, rdx
0x180013815  mov     r14, rcx
0x180013818  xor     ecx, ecx
0x18001381a  call    __scrt_initialize_crt
0x18001381f  test    al, al
0x180013821  jz      loc_1800138EA
0x180013827  call    __scrt_acquire_startup_lock
0x18001382c  mov     bl, al
0x18001382e  mov     [rsp+48h+arg_10], al
0x180013832  mov     dil, 1
0x180013835  cmp     cs:__scrt_current_native_startup_state, 0
0x18001383c  jnz     loc_1800138F6
0x180013842  mov     cs:__scrt_current_native_startup_state, 1
0x18001384c  call    __scrt_dllmain_before_initialize_c
0x180013851  test    al, al
0x180013853  jz      short loc_1800138A4
0x180013855  call    _RTC_Initialize
0x18001385a  call    ?__scrt_initialize_type_info@@YAXXZ; __scrt_initialize_type_info(void)
0x18001385f  call    __scrt_initialize_default_local_stdio_options
0x180013864  lea     rdx, __xi_z; Last
0x18001386b  lea     rcx, __xi_a; First
0x180013872  call    _initterm_e_0
0x180013877  test    eax, eax
0x180013879  jnz     short loc_1800138A4
0x18001387b  call    __scrt_dllmain_after_initialize_c
0x180013880  test    al, al
0x180013882  jz      short loc_1800138A4
0x180013884  lea     rdx, __xc_z; Last
0x18001388b  lea     rcx, __xc_a; First
0x180013892  call    _initterm_0
0x180013897  mov     cs:__scrt_current_native_startup_state, 2
0x1800138a1  xor     dil, dil
0x1800138a4  mov     cl, bl
0x1800138a6  call    __scrt_release_startup_lock
0x1800138ab  test    dil, dil
0x1800138ae  jnz     short loc_1800138EA
0x1800138b0  call    __scrt_get_dyn_tls_init_callback
0x1800138b5  mov     rbx, rax
0x1800138b8  cmp     qword ptr [rax], 0
0x1800138bc  jz      short loc_1800138DD
0x1800138be  mov     rcx, rax
0x1800138c1  call    __scrt_is_nonwritable_in_current_image
0x1800138c6  test    al, al
0x1800138c8  jz      short loc_1800138DD
0x1800138ca  mov     r8, rsi
0x1800138cd  mov     edx, 2
0x1800138d2  mov     rcx, r14
0x1800138d5  mov     rax, [rbx]
0x1800138d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138dd  inc     cs:dword_1800335D0
0x1800138e3  mov     eax, 1
0x1800138e8  jmp     short loc_1800138EC
0x1800138ea  xor     eax, eax
0x1800138ec  add     rsp, 28h
0x1800138f0  pop     r14
0x1800138f2  pop     rdi
0x1800138f3  pop     rsi
0x1800138f4  pop     rbx
0x1800138f5  retn
0x1800138f6  mov     ecx, 7
0x1800138fb  call    __scrt_fastfail
0x180026172  push    rbp
0x180026174  sub     rsp, 20h
0x180026178  mov     rbp, rdx
0x18002617b  mov     cl, [rbp+60h]
0x18002617e  add     rsp, 20h
0x180026182  pop     rbp
0x180026183  jmp     __scrt_release_startup_lock
```
