# dllmain_crt_process_detach

- ea: `0x1800012f8`
- end: `0x18000137b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800011a0`

## callees

- `0x1800012f8`
- `0x180001610`
- `0x180001738`
- `0x180001770`
- `0x180001900`
- `0x18000192c`
- `0x180001e1c`
- `0x180001e64`
- `0x180001eb4`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  __int64 v3; // rcx
  char v4; // bl
  __int64 v5; // rcx
  __int64 v6; // rcx
  unsigned int v7; // ebx
  __int64 v8; // rcx

  if ( dword_180028370 <= 0 )
    return 0;
  --dword_180028370;
  v4 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
    _scrt_fastfail(7);
  _scrt_dllmain_uninitialize_c(v3);
  __scrt_uninitialize_type_info();
  RTC_Terminate();
  _scrt_current_native_startup_state = 0;
  LOBYTE(v5) = v4;
  _scrt_release_startup_lock(v5);
  LOBYTE(v6) = a1;
  v7 = (unsigned __int8)_scrt_uninitialize_crt(v6, 0);
  _scrt_dllmain_uninitialize_critical(v8);
  return v7;
}

```

## disassembly

```asm
0x1800012f8  mov     [rsp+arg_0], rbx
0x1800012fd  push    rdi
0x1800012fe  sub     rsp, 30h
0x180001302  mov     dil, cl
0x180001305  mov     eax, cs:dword_180028370
0x18000130b  test    eax, eax
0x18000130d  jg      short loc_18000131C
0x18000130f  xor     eax, eax
0x180001311  mov     rbx, [rsp+38h+arg_0]
0x180001316  add     rsp, 30h
0x18000131a  pop     rdi
0x18000131b  retn
0x18000131c  dec     eax
0x18000131e  mov     cs:dword_180028370, eax
0x180001324  call    __scrt_acquire_startup_lock
0x180001329  mov     bl, al
0x18000132b  mov     [rsp+38h+var_18], al
0x18000132f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001336  jnz     short loc_18000136E
0x180001338  call    __scrt_dllmain_uninitialize_c
0x18000133d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001342  call    _RTC_Terminate
0x180001347  mov     cs:__scrt_current_native_startup_state, 0
0x180001351  mov     cl, bl
0x180001353  call    __scrt_release_startup_lock
0x180001358  xor     edx, edx
0x18000135a  mov     cl, dil
0x18000135d  call    __scrt_uninitialize_crt
0x180001362  movzx   ebx, al
0x180001365  call    __scrt_dllmain_uninitialize_critical
0x18000136a  mov     eax, ebx
0x18000136c  jmp     short loc_180001311
0x18000136e  mov     ecx, 7
0x180001373  call    __scrt_fastfail
0x18001cee9  push    rbp
0x18001ceeb  sub     rsp, 20h
0x18001ceef  mov     rbp, rdx
0x18001cef2  mov     cl, [rbp+20h]
0x18001cef5  call    __scrt_release_startup_lock
0x18001cefa  nop
0x18001cefb  add     rsp, 20h
0x18001ceff  pop     rbp
0x18001cf00  retn
0x18001cf02  push    rbp
0x18001cf04  sub     rsp, 20h
0x18001cf08  mov     rbp, rdx
0x18001cf0b  add     rsp, 20h
0x18001cf0f  pop     rbp
0x18001cf10  jmp     __scrt_dllmain_uninitialize_critical
```
