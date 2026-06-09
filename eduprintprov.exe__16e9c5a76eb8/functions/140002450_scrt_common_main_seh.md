# __scrt_common_main_seh

- ea: `0x140002450`
- end: `0x1400025c0`
- name: `__scrt_common_main_seh`
- size: `368`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x1400025d0`

## callees

- `0x140002450`
- `0x140002674`
- `0x1400026b4`
- `0x140002788`
- `0x140002828`
- `0x140002854`
- `0x140002d7c`
- `0x140002d8c`
- `0x140002d9c`
- `0x140002da8`
- `0x140002df4`
- `0x140002fc6`
- `0x140002fd2`
- `0x140002fde`
- `0x140002fea`
- `0x14000304a`
- `0x14000307a`
- `0x140003086`
- `0x1400030d8`
- `0x140003108`
- `0x140012e44`
- `0x140014010`

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
  v14 = WinMain(&_ImageBase, 0, narrow_winmain_command_line_0, show_window_mode);
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
0x140002450  mov     [rsp+arg_0], rbx
0x140002455  push    rdi
0x140002456  sub     rsp, 30h
0x14000245a  mov     ecx, 1
0x14000245f  call    __scrt_initialize_crt
0x140002464  test    al, al
0x140002466  jz      loc_14000259B
0x14000246c  xor     dil, dil
0x14000246f  mov     [rsp+38h+var_18], dil
0x140002474  call    __scrt_acquire_startup_lock
0x140002479  mov     bl, al
0x14000247b  mov     ecx, cs:__scrt_current_native_startup_state
0x140002481  cmp     ecx, 1
0x140002484  jz      loc_1400025A6
0x14000248a  test    ecx, ecx
0x14000248c  jnz     short loc_1400024D8
0x14000248e  mov     cs:__scrt_current_native_startup_state, 1
0x140002498  lea     rdx, __xi_z; Last
0x14000249f  lea     rcx, __xi_a; First
0x1400024a6  call    _initterm_e_0
0x1400024ab  test    eax, eax
0x1400024ad  jz      short loc_1400024B9
0x1400024af  mov     eax, 0FFh
0x1400024b4  jmp     loc_140002590
0x1400024b9  lea     rdx, __xc_z; Last
0x1400024c0  lea     rcx, __xc_a; First
0x1400024c7  call    _initterm_0
0x1400024cc  mov     cs:__scrt_current_native_startup_state, 2
0x1400024d6  jmp     short loc_1400024E0
0x1400024d8  mov     dil, 1
0x1400024db  mov     [rsp+38h+var_18], dil
0x1400024e0  mov     cl, bl
0x1400024e2  call    __scrt_release_startup_lock
0x1400024e7  call    __scrt_get_dyn_tls_init_callback
0x1400024ec  mov     rbx, rax
0x1400024ef  cmp     qword ptr [rax], 0
0x1400024f3  jz      short loc_140002512
0x1400024f5  mov     rcx, rax
0x1400024f8  call    __scrt_is_nonwritable_in_current_image
0x1400024fd  test    al, al
0x1400024ff  jz      short loc_140002512
0x140002501  xor     r8d, r8d
0x140002504  lea     edx, [r8+2]
0x140002508  xor     ecx, ecx
0x14000250a  mov     rax, [rbx]
0x14000250d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002512  call    __scrt_get_dyn_tls_dtor_callback
0x140002517  mov     rbx, rax
0x14000251a  cmp     qword ptr [rax], 0
0x14000251e  jz      short loc_140002534
0x140002520  mov     rcx, rax
0x140002523  call    __scrt_is_nonwritable_in_current_image
0x140002528  test    al, al
0x14000252a  jz      short loc_140002534
0x14000252c  mov     rcx, [rbx]; Callback
0x14000252f  call    _register_thread_local_exe_atexit_callback_0
0x140002534  call    __scrt_get_show_window_mode
0x140002539  movzx   ebx, ax
0x14000253c  call    _o__get_narrow_winmain_command_line_0
0x140002541  mov     r9d, ebx; nShowCmd
0x140002544  mov     r8, rax; lpCmdLine
0x140002547  xor     edx, edx; hPrevInstance
0x140002549  lea     rcx, __ImageBase; hInstance
0x140002550  call    WinMain
0x140002555  mov     ebx, eax
0x140002557  call    __scrt_is_managed_app
0x14000255c  test    al, al
0x14000255e  jz      short loc_1400025B0
0x140002560  test    dil, dil
0x140002563  jnz     short loc_14000256A
0x140002565  call    _o__cexit_0
0x14000256a  xor     edx, edx
0x14000256c  mov     cl, 1
0x14000256e  call    __scrt_uninitialize_crt
0x140002573  mov     eax, ebx
0x140002575  jmp     short loc_140002590
0x140002577  mov     ebx, eax
0x140002579  call    __scrt_is_managed_app
0x14000257e  test    al, al
0x140002580  jz      short loc_1400025B8
0x140002582  cmp     [rsp+38h+var_18], 0
0x140002587  jnz     short loc_14000258E
0x140002589  call    _c_exit_0
0x14000258e  mov     eax, ebx
0x140002590  mov     rbx, [rsp+38h+arg_0]
0x140002595  add     rsp, 30h
0x140002599  pop     rdi
0x14000259a  retn
0x14000259b  mov     ecx, 7
0x1400025a0  call    __scrt_fastfail
0x1400025a6  mov     ecx, 7
0x1400025ab  call    __scrt_fastfail
0x1400025b0  mov     ecx, ebx; Code
0x1400025b2  call    _o_exit_0
0x1400025b8  mov     ecx, ebx
0x1400025ba  call    _o__exit_0
0x1400025bf  nop
0x14001319c  push    rbp
0x14001319e  sub     rsp, 20h
0x1400131a2  mov     rbp, rdx
0x1400131a5  mov     rdx, rcx; ExceptionPtr
0x1400131a8  mov     rcx, [rcx]
0x1400131ab  mov     ecx, [rcx]; ExceptionNum
0x1400131ad  call    _seh_filter_exe
0x1400131b2  nop
0x1400131b3  add     rsp, 20h
0x1400131b7  pop     rbp
0x1400131b8  retn
```
