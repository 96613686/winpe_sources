# __scrt_common_main_seh

- ea: `0x1400011d0`
- end: `0x140001340`
- name: `__scrt_common_main_seh`
- size: `368`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x140001350`

## callees

- `0x1400011d0`
- `0x1400013a4`
- `0x1400013e4`
- `0x1400014b8`
- `0x140001558`
- `0x140001584`
- `0x140001750`
- `0x140001760`
- `0x140001770`
- `0x14000177c`
- `0x1400017c8`
- `0x140001bf6`
- `0x140001c02`
- `0x140001c0e`
- `0x140001c1a`
- `0x140001c3e`
- `0x140001c6e`
- `0x140001c7a`
- `0x140001caa`
- `0x140001cda`
- `0x140002fa8`
- `0x140004010`

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
  WCHAR *wide_winmain_command_line_0; // rax
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
  wide_winmain_command_line_0 = (WCHAR *)o__get_wide_winmain_command_line_0();
  v14 = wWinMain((HINSTANCE)0x140000000LL, 0, wide_winmain_command_line_0, show_window_mode);
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
0x1400011d0  mov     [rsp+arg_0], rbx
0x1400011d5  push    rdi
0x1400011d6  sub     rsp, 30h
0x1400011da  mov     ecx, 1
0x1400011df  call    __scrt_initialize_crt
0x1400011e4  test    al, al
0x1400011e6  jz      loc_14000131B
0x1400011ec  xor     dil, dil
0x1400011ef  mov     [rsp+38h+var_18], dil
0x1400011f4  call    __scrt_acquire_startup_lock
0x1400011f9  mov     bl, al
0x1400011fb  mov     ecx, cs:__scrt_current_native_startup_state
0x140001201  cmp     ecx, 1
0x140001204  jz      loc_140001326
0x14000120a  test    ecx, ecx
0x14000120c  jnz     short loc_140001258
0x14000120e  mov     cs:__scrt_current_native_startup_state, 1
0x140001218  lea     rdx, __xi_z; Last
0x14000121f  lea     rcx, __xi_a; First
0x140001226  call    _initterm_e_0
0x14000122b  test    eax, eax
0x14000122d  jz      short loc_140001239
0x14000122f  mov     eax, 0FFh
0x140001234  jmp     loc_140001310
0x140001239  lea     rdx, __xc_z; Last
0x140001240  lea     rcx, __xc_a; First
0x140001247  call    _initterm_0
0x14000124c  mov     cs:__scrt_current_native_startup_state, 2
0x140001256  jmp     short loc_140001260
0x140001258  mov     dil, 1
0x14000125b  mov     [rsp+38h+var_18], dil
0x140001260  mov     cl, bl
0x140001262  call    __scrt_release_startup_lock
0x140001267  call    __scrt_get_dyn_tls_init_callback
0x14000126c  mov     rbx, rax
0x14000126f  cmp     qword ptr [rax], 0
0x140001273  jz      short loc_140001292
0x140001275  mov     rcx, rax
0x140001278  call    __scrt_is_nonwritable_in_current_image
0x14000127d  test    al, al
0x14000127f  jz      short loc_140001292
0x140001281  xor     r8d, r8d
0x140001284  lea     edx, [r8+2]
0x140001288  xor     ecx, ecx
0x14000128a  mov     rax, [rbx]
0x14000128d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001292  call    __scrt_get_dyn_tls_dtor_callback
0x140001297  mov     rbx, rax
0x14000129a  cmp     qword ptr [rax], 0
0x14000129e  jz      short loc_1400012B4
0x1400012a0  mov     rcx, rax
0x1400012a3  call    __scrt_is_nonwritable_in_current_image
0x1400012a8  test    al, al
0x1400012aa  jz      short loc_1400012B4
0x1400012ac  mov     rcx, [rbx]; Callback
0x1400012af  call    _register_thread_local_exe_atexit_callback_0
0x1400012b4  call    __scrt_get_show_window_mode
0x1400012b9  movzx   ebx, ax
0x1400012bc  call    _o__get_wide_winmain_command_line_0
0x1400012c1  mov     r9d, ebx; nShowCmd
0x1400012c4  mov     r8, rax; lpCmdLine
0x1400012c7  xor     edx, edx; hPrevInstance
0x1400012c9  lea     rcx, cs:140000000h; hInstance
0x1400012d0  call    wWinMain
0x1400012d5  mov     ebx, eax
0x1400012d7  call    __scrt_is_managed_app
0x1400012dc  test    al, al
0x1400012de  jz      short loc_140001330
0x1400012e0  test    dil, dil
0x1400012e3  jnz     short loc_1400012EA
0x1400012e5  call    _o__cexit_0
0x1400012ea  xor     edx, edx
0x1400012ec  mov     cl, 1
0x1400012ee  call    __scrt_uninitialize_crt
0x1400012f3  mov     eax, ebx
0x1400012f5  jmp     short loc_140001310
0x1400012f7  mov     ebx, eax
0x1400012f9  call    __scrt_is_managed_app
0x1400012fe  test    al, al
0x140001300  jz      short loc_140001338
0x140001302  cmp     [rsp+38h+var_18], 0
0x140001307  jnz     short loc_14000130E
0x140001309  call    _c_exit_0
0x14000130e  mov     eax, ebx
0x140001310  mov     rbx, [rsp+38h+arg_0]
0x140001315  add     rsp, 30h
0x140001319  pop     rdi
0x14000131a  retn
0x14000131b  mov     ecx, 7
0x140001320  call    __scrt_fastfail
0x140001326  mov     ecx, 7
0x14000132b  call    __scrt_fastfail
0x140001330  mov     ecx, ebx; Code
0x140001332  call    _o_exit_0
0x140001338  mov     ecx, ebx
0x14000133a  call    _o__exit_0
0x14000133f  nop
0x14000331c  push    rbp
0x14000331e  sub     rsp, 20h
0x140003322  mov     rbp, rdx
0x140003325  mov     rdx, rcx; ExceptionPtr
0x140003328  mov     rcx, [rcx]
0x14000332b  mov     ecx, [rcx]; ExceptionNum
0x14000332d  call    _seh_filter_exe
0x140003332  nop
0x140003333  add     rsp, 20h
0x140003337  pop     rbp
0x140003338  retn
```
