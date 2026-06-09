# __scrt_common_main_seh

- ea: `0x1400012c0`
- end: `0x140001430`
- name: `__scrt_common_main_seh`
- size: `368`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x140001440`

## callees

- `0x1400012c0`
- `0x1400014b8`
- `0x1400014f8`
- `0x1400015cc`
- `0x14000166c`
- `0x140001698`
- `0x140001850`
- `0x140001860`
- `0x140001870`
- `0x14000187c`
- `0x1400018c8`
- `0x140001cf6`
- `0x140001d02`
- `0x140001d0e`
- `0x140001d1a`
- `0x140001d4a`
- `0x140001d7a`
- `0x140001d86`
- `0x140001dc2`
- `0x140001df2`
- `0x14000568c`
- `0x140006010`

## pseudocode

```c
__int64 _scrt_common_main_seh()
{
  __int64 v0; // rcx
  char v1; // di
  char v2; // bl
  __int64 v3; // rcx
  __int64 v5; // rcx
  _QWORD *dyn_tls_init_callback; // rax
  __int64 v7; // rcx
  void (__fastcall **v8)(_QWORD, __int64); // rbx
  _tls_callback_type *dyn_tls_dtor_callback; // rax
  __int64 v10; // rcx
  _tls_callback_type *v11; // rbx
  int show_window_mode; // ebx
  CHAR *narrow_winmain_command_line_0; // rax
  unsigned int v14; // ebx
  __int64 v15; // rcx
  __int64 v16; // rcx

  if ( !(unsigned __int8)_scrt_initialize_crt(1) )
    _scrt_fastfail(7);
  v1 = 0;
  v2 = _scrt_acquire_startup_lock(v0);
  v3 = (unsigned int)_scrt_current_native_startup_state;
  if ( _scrt_current_native_startup_state == 1 )
    _scrt_fastfail(7);
  if ( _scrt_current_native_startup_state )
  {
    v1 = 1;
  }
  else
  {
    _scrt_current_native_startup_state = 1;
    if ( initterm_e_0((_PIFV *)&_xi_a, (_PIFV *)&_xi_z) )
      return 255;
    initterm_0((_PVFV *)&_xc_a, (_PVFV *)&_xc_z);
    _scrt_current_native_startup_state = 2;
  }
  LOBYTE(v3) = v2;
  _scrt_release_startup_lock(v3);
  dyn_tls_init_callback = (_QWORD *)_scrt_get_dyn_tls_init_callback(v5);
  v8 = (void (__fastcall **)(_QWORD, __int64))dyn_tls_init_callback;
  if ( *dyn_tls_init_callback && (unsigned __int8)_scrt_is_nonwritable_in_current_image(dyn_tls_init_callback) )
    (*v8)(0, 2);
  dyn_tls_dtor_callback = (_tls_callback_type *)_scrt_get_dyn_tls_dtor_callback(v7);
  v11 = dyn_tls_dtor_callback;
  if ( *dyn_tls_dtor_callback && (unsigned __int8)_scrt_is_nonwritable_in_current_image(dyn_tls_dtor_callback) )
    register_thread_local_exe_atexit_callback_0(*v11);
  show_window_mode = (unsigned __int16)_scrt_get_show_window_mode(v10);
  narrow_winmain_command_line_0 = (CHAR *)o__get_narrow_winmain_command_line_0();
  v14 = WinMain((HINSTANCE)0x140000000LL, 0, narrow_winmain_command_line_0, show_window_mode);
  if ( !(unsigned __int8)_scrt_is_managed_app(v15) )
    o_exit_0(v14);
  if ( !v1 )
    o__cexit_0(v16);
  LOBYTE(v16) = 1;
  _scrt_uninitialize_crt(v16, 0);
  return v14;
}

```

## disassembly

```asm
0x1400012c0  mov     [rsp+arg_0], rbx
0x1400012c5  push    rdi
0x1400012c6  sub     rsp, 30h
0x1400012ca  mov     ecx, 1
0x1400012cf  call    __scrt_initialize_crt
0x1400012d4  test    al, al
0x1400012d6  jz      loc_14000140B
0x1400012dc  xor     dil, dil
0x1400012df  mov     [rsp+38h+var_18], dil
0x1400012e4  call    __scrt_acquire_startup_lock
0x1400012e9  mov     bl, al
0x1400012eb  mov     ecx, cs:__scrt_current_native_startup_state
0x1400012f1  cmp     ecx, 1
0x1400012f4  jz      loc_140001416
0x1400012fa  test    ecx, ecx
0x1400012fc  jnz     short loc_140001348
0x1400012fe  mov     cs:__scrt_current_native_startup_state, 1
0x140001308  lea     rdx, __xi_z; Last
0x14000130f  lea     rcx, __xi_a; First
0x140001316  call    _initterm_e_0
0x14000131b  test    eax, eax
0x14000131d  jz      short loc_140001329
0x14000131f  mov     eax, 0FFh
0x140001324  jmp     loc_140001400
0x140001329  lea     rdx, __xc_z; Last
0x140001330  lea     rcx, __xc_a; First
0x140001337  call    _initterm_0
0x14000133c  mov     cs:__scrt_current_native_startup_state, 2
0x140001346  jmp     short loc_140001350
0x140001348  mov     dil, 1
0x14000134b  mov     [rsp+38h+var_18], dil
0x140001350  mov     cl, bl
0x140001352  call    __scrt_release_startup_lock
0x140001357  call    __scrt_get_dyn_tls_init_callback
0x14000135c  mov     rbx, rax
0x14000135f  cmp     qword ptr [rax], 0
0x140001363  jz      short loc_140001382
0x140001365  mov     rcx, rax
0x140001368  call    __scrt_is_nonwritable_in_current_image
0x14000136d  test    al, al
0x14000136f  jz      short loc_140001382
0x140001371  xor     r8d, r8d
0x140001374  lea     edx, [r8+2]
0x140001378  xor     ecx, ecx
0x14000137a  mov     rax, [rbx]
0x14000137d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001382  call    __scrt_get_dyn_tls_dtor_callback
0x140001387  mov     rbx, rax
0x14000138a  cmp     qword ptr [rax], 0
0x14000138e  jz      short loc_1400013A4
0x140001390  mov     rcx, rax
0x140001393  call    __scrt_is_nonwritable_in_current_image
0x140001398  test    al, al
0x14000139a  jz      short loc_1400013A4
0x14000139c  mov     rcx, [rbx]; Callback
0x14000139f  call    _register_thread_local_exe_atexit_callback_0
0x1400013a4  call    __scrt_get_show_window_mode
0x1400013a9  movzx   ebx, ax
0x1400013ac  call    _o__get_narrow_winmain_command_line_0
0x1400013b1  mov     r9d, ebx; nShowCmd
0x1400013b4  mov     r8, rax; lpCmdLine
0x1400013b7  xor     edx, edx; hPrevInstance
0x1400013b9  lea     rcx, cs:140000000h; hInstance
0x1400013c0  call    WinMain
0x1400013c5  mov     ebx, eax
0x1400013c7  call    __scrt_is_managed_app
0x1400013cc  test    al, al
0x1400013ce  jz      short loc_140001420
0x1400013d0  test    dil, dil
0x1400013d3  jnz     short loc_1400013DA
0x1400013d5  call    _o__cexit_0
0x1400013da  xor     edx, edx
0x1400013dc  mov     cl, 1
0x1400013de  call    __scrt_uninitialize_crt
0x1400013e3  mov     eax, ebx
0x1400013e5  jmp     short loc_140001400
0x1400013e7  mov     ebx, eax
0x1400013e9  call    __scrt_is_managed_app
0x1400013ee  test    al, al
0x1400013f0  jz      short loc_140001428
0x1400013f2  cmp     [rsp+38h+var_18], 0
0x1400013f7  jnz     short loc_1400013FE
0x1400013f9  call    _c_exit_0
0x1400013fe  mov     eax, ebx
0x140001400  mov     rbx, [rsp+38h+arg_0]
0x140001405  add     rsp, 30h
0x140001409  pop     rdi
0x14000140a  retn
0x14000140b  mov     ecx, 7
0x140001410  call    __scrt_fastfail
0x140001416  mov     ecx, 7
0x14000141b  call    __scrt_fastfail
0x140001420  mov     ecx, ebx; Code
0x140001422  call    _o_exit_0
0x140001428  mov     ecx, ebx
0x14000142a  call    _o__exit_0
0x14000142f  nop
0x140005bcc  push    rbp
0x140005bce  sub     rsp, 20h
0x140005bd2  mov     rbp, rdx
0x140005bd5  mov     rdx, rcx; ExceptionPtr
0x140005bd8  mov     rcx, [rcx]
0x140005bdb  mov     ecx, [rcx]; ExceptionNum
0x140005bdd  call    _seh_filter_exe
0x140005be2  nop
0x140005be3  add     rsp, 20h
0x140005be7  pop     rbp
0x140005be8  retn
```
