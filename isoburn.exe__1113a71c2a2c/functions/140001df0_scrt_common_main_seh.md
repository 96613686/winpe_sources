# __scrt_common_main_seh

- ea: `0x140001df0`
- end: `0x140001f60`
- name: `__scrt_common_main_seh`
- size: `368`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x140001f70`

## callees

- `0x140001df0`
- `0x140001fd0`
- `0x140002010`
- `0x1400020e4`
- `0x140002184`
- `0x1400021b0`
- `0x1400025fc`
- `0x14000260c`
- `0x14000261c`
- `0x140002628`
- `0x140002674`
- `0x140002a76`
- `0x140002a82`
- `0x140002a8e`
- `0x140002a9a`
- `0x140002ad6`
- `0x140002b06`
- `0x140002b12`
- `0x140002b4e`
- `0x140002b7e`
- `0x14000ed60`
- `0x140010010`

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
0x140001df0  mov     [rsp+arg_0], rbx
0x140001df5  push    rdi
0x140001df6  sub     rsp, 30h
0x140001dfa  mov     ecx, 1
0x140001dff  call    __scrt_initialize_crt
0x140001e04  test    al, al
0x140001e06  jz      loc_140001F3B
0x140001e0c  xor     dil, dil
0x140001e0f  mov     [rsp+38h+var_18], dil
0x140001e14  call    __scrt_acquire_startup_lock
0x140001e19  mov     bl, al
0x140001e1b  mov     ecx, cs:__scrt_current_native_startup_state
0x140001e21  cmp     ecx, 1
0x140001e24  jz      loc_140001F46
0x140001e2a  test    ecx, ecx
0x140001e2c  jnz     short loc_140001E78
0x140001e2e  mov     cs:__scrt_current_native_startup_state, 1
0x140001e38  lea     rdx, __xi_z; Last
0x140001e3f  lea     rcx, __xi_a; First
0x140001e46  call    _initterm_e_0
0x140001e4b  test    eax, eax
0x140001e4d  jz      short loc_140001E59
0x140001e4f  mov     eax, 0FFh
0x140001e54  jmp     loc_140001F30
0x140001e59  lea     rdx, __xc_z; Last
0x140001e60  lea     rcx, __xc_a; First
0x140001e67  call    _initterm_0
0x140001e6c  mov     cs:__scrt_current_native_startup_state, 2
0x140001e76  jmp     short loc_140001E80
0x140001e78  mov     dil, 1
0x140001e7b  mov     [rsp+38h+var_18], dil
0x140001e80  mov     cl, bl
0x140001e82  call    __scrt_release_startup_lock
0x140001e87  call    __scrt_get_dyn_tls_init_callback
0x140001e8c  mov     rbx, rax
0x140001e8f  cmp     qword ptr [rax], 0
0x140001e93  jz      short loc_140001EB2
0x140001e95  mov     rcx, rax
0x140001e98  call    __scrt_is_nonwritable_in_current_image
0x140001e9d  test    al, al
0x140001e9f  jz      short loc_140001EB2
0x140001ea1  xor     r8d, r8d
0x140001ea4  lea     edx, [r8+2]
0x140001ea8  xor     ecx, ecx
0x140001eaa  mov     rax, [rbx]
0x140001ead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001eb2  call    __scrt_get_dyn_tls_dtor_callback
0x140001eb7  mov     rbx, rax
0x140001eba  cmp     qword ptr [rax], 0
0x140001ebe  jz      short loc_140001ED4
0x140001ec0  mov     rcx, rax
0x140001ec3  call    __scrt_is_nonwritable_in_current_image
0x140001ec8  test    al, al
0x140001eca  jz      short loc_140001ED4
0x140001ecc  mov     rcx, [rbx]; Callback
0x140001ecf  call    _register_thread_local_exe_atexit_callback_0
0x140001ed4  call    __scrt_get_show_window_mode
0x140001ed9  movzx   ebx, ax
0x140001edc  call    _o__get_narrow_winmain_command_line_0
0x140001ee1  mov     r9d, ebx; nShowCmd
0x140001ee4  mov     r8, rax; lpCmdLine
0x140001ee7  xor     edx, edx; hPrevInstance
0x140001ee9  lea     rcx, cs:140000000h; hInstance
0x140001ef0  call    WinMain
0x140001ef5  mov     ebx, eax
0x140001ef7  call    __scrt_is_managed_app
0x140001efc  test    al, al
0x140001efe  jz      short loc_140001F50
0x140001f00  test    dil, dil
0x140001f03  jnz     short loc_140001F0A
0x140001f05  call    _o__cexit_0
0x140001f0a  xor     edx, edx
0x140001f0c  mov     cl, 1
0x140001f0e  call    __scrt_uninitialize_crt
0x140001f13  mov     eax, ebx
0x140001f15  jmp     short loc_140001F30
0x140001f17  mov     ebx, eax
0x140001f19  call    __scrt_is_managed_app
0x140001f1e  test    al, al
0x140001f20  jz      short loc_140001F58
0x140001f22  cmp     [rsp+38h+var_18], 0
0x140001f27  jnz     short loc_140001F2E
0x140001f29  call    _c_exit_0
0x140001f2e  mov     eax, ebx
0x140001f30  mov     rbx, [rsp+38h+arg_0]
0x140001f35  add     rsp, 30h
0x140001f39  pop     rdi
0x140001f3a  retn
0x140001f3b  mov     ecx, 7
0x140001f40  call    __scrt_fastfail
0x140001f46  mov     ecx, 7
0x140001f4b  call    __scrt_fastfail
0x140001f50  mov     ecx, ebx; Code
0x140001f52  call    _o_exit_0
0x140001f58  mov     ecx, ebx
0x140001f5a  call    _o__exit_0
0x140001f5f  nop
0x14000f7bc  push    rbp
0x14000f7be  sub     rsp, 20h
0x14000f7c2  mov     rbp, rdx
0x14000f7c5  mov     rdx, rcx; ExceptionPtr
0x14000f7c8  mov     rcx, [rcx]
0x14000f7cb  mov     ecx, [rcx]; ExceptionNum
0x14000f7cd  call    _seh_filter_exe
0x14000f7d2  nop
0x14000f7d3  add     rsp, 20h
0x14000f7d7  pop     rbp
0x14000f7d8  retn
```
