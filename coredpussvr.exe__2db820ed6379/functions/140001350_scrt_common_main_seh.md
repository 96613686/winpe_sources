# __scrt_common_main_seh

- ea: `0x140001350`
- end: `0x1400014c0`
- name: `__scrt_common_main_seh`
- size: `368`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x1400014d0`

## callees

- `0x140001350`
- `0x140001524`
- `0x140001564`
- `0x140001638`
- `0x1400016d8`
- `0x140001704`
- `0x1400019a0`
- `0x1400019b0`
- `0x1400019c0`
- `0x1400019cc`
- `0x140001a18`
- `0x140001fb6`
- `0x140001fc2`
- `0x140001fce`
- `0x140001fda`
- `0x140002046`
- `0x140002076`
- `0x140002082`
- `0x1400020d8`
- `0x140002108`
- `0x140008b18`
- `0x14000a010`

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
0x140001350  mov     [rsp+arg_0], rbx
0x140001355  push    rdi
0x140001356  sub     rsp, 30h
0x14000135a  mov     ecx, 1
0x14000135f  call    __scrt_initialize_crt
0x140001364  test    al, al
0x140001366  jz      loc_14000149B
0x14000136c  xor     dil, dil
0x14000136f  mov     [rsp+38h+var_18], dil
0x140001374  call    __scrt_acquire_startup_lock
0x140001379  mov     bl, al
0x14000137b  mov     ecx, cs:__scrt_current_native_startup_state
0x140001381  cmp     ecx, 1
0x140001384  jz      loc_1400014A6
0x14000138a  test    ecx, ecx
0x14000138c  jnz     short loc_1400013D8
0x14000138e  mov     cs:__scrt_current_native_startup_state, 1
0x140001398  lea     rdx, __xi_z; Last
0x14000139f  lea     rcx, __xi_a; First
0x1400013a6  call    _initterm_e_0
0x1400013ab  test    eax, eax
0x1400013ad  jz      short loc_1400013B9
0x1400013af  mov     eax, 0FFh
0x1400013b4  jmp     loc_140001490
0x1400013b9  lea     rdx, __xc_z; Last
0x1400013c0  lea     rcx, __xc_a; First
0x1400013c7  call    _initterm_0
0x1400013cc  mov     cs:__scrt_current_native_startup_state, 2
0x1400013d6  jmp     short loc_1400013E0
0x1400013d8  mov     dil, 1
0x1400013db  mov     [rsp+38h+var_18], dil
0x1400013e0  mov     cl, bl
0x1400013e2  call    __scrt_release_startup_lock
0x1400013e7  call    __scrt_get_dyn_tls_init_callback
0x1400013ec  mov     rbx, rax
0x1400013ef  cmp     qword ptr [rax], 0
0x1400013f3  jz      short loc_140001412
0x1400013f5  mov     rcx, rax
0x1400013f8  call    __scrt_is_nonwritable_in_current_image
0x1400013fd  test    al, al
0x1400013ff  jz      short loc_140001412
0x140001401  xor     r8d, r8d
0x140001404  lea     edx, [r8+2]
0x140001408  xor     ecx, ecx
0x14000140a  mov     rax, [rbx]
0x14000140d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001412  call    __scrt_get_dyn_tls_dtor_callback
0x140001417  mov     rbx, rax
0x14000141a  cmp     qword ptr [rax], 0
0x14000141e  jz      short loc_140001434
0x140001420  mov     rcx, rax
0x140001423  call    __scrt_is_nonwritable_in_current_image
0x140001428  test    al, al
0x14000142a  jz      short loc_140001434
0x14000142c  mov     rcx, [rbx]; Callback
0x14000142f  call    _register_thread_local_exe_atexit_callback_0
0x140001434  call    __scrt_get_show_window_mode
0x140001439  movzx   ebx, ax
0x14000143c  call    _o__get_narrow_winmain_command_line_0
0x140001441  mov     r9d, ebx; nShowCmd
0x140001444  mov     r8, rax; lpCmdLine
0x140001447  xor     edx, edx; hPrevInstance
0x140001449  lea     rcx, __ImageBase; hInstance
0x140001450  call    WinMain
0x140001455  mov     ebx, eax
0x140001457  call    __scrt_is_managed_app
0x14000145c  test    al, al
0x14000145e  jz      short loc_1400014B0
0x140001460  test    dil, dil
0x140001463  jnz     short loc_14000146A
0x140001465  call    _o__cexit_0
0x14000146a  xor     edx, edx
0x14000146c  mov     cl, 1
0x14000146e  call    __scrt_uninitialize_crt
0x140001473  mov     eax, ebx
0x140001475  jmp     short loc_140001490
0x140001477  mov     ebx, eax
0x140001479  call    __scrt_is_managed_app
0x14000147e  test    al, al
0x140001480  jz      short loc_1400014B8
0x140001482  cmp     [rsp+38h+var_18], 0
0x140001487  jnz     short loc_14000148E
0x140001489  call    _c_exit_0
0x14000148e  mov     eax, ebx
0x140001490  mov     rbx, [rsp+38h+arg_0]
0x140001495  add     rsp, 30h
0x140001499  pop     rdi
0x14000149a  retn
0x14000149b  mov     ecx, 7
0x1400014a0  call    __scrt_fastfail
0x1400014a6  mov     ecx, 7
0x1400014ab  call    __scrt_fastfail
0x1400014b0  mov     ecx, ebx; Code
0x1400014b2  call    _o_exit_0
0x1400014b8  mov     ecx, ebx
0x1400014ba  call    _o__exit_0
0x1400014bf  nop
0x14000910c  push    rbp
0x14000910e  sub     rsp, 20h
0x140009112  mov     rbp, rdx
0x140009115  mov     rdx, rcx; ExceptionPtr
0x140009118  mov     rcx, [rcx]
0x14000911b  mov     ecx, [rcx]; ExceptionNum
0x14000911d  call    _seh_filter_exe
0x140009122  nop
0x140009123  add     rsp, 20h
0x140009127  pop     rbp
0x140009128  retn
```
