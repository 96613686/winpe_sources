# dllmain_crt_process_detach

- ea: `0x180004a28`
- end: `0x180004aab`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800048d0`

## callees

- `0x180004a28`
- `0x180004d34`
- `0x180004d6c`
- `0x180004e94`
- `0x180004ecc`
- `0x18000505c`
- `0x180005088`
- `0x1800050c8`
- `0x180005118`

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

  if ( dword_18000E510 <= 0 )
    return 0;
  --dword_18000E510;
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
0x180004a28  mov     [rsp+arg_0], rbx
0x180004a2d  push    rdi
0x180004a2e  sub     rsp, 30h
0x180004a32  mov     dil, cl
0x180004a35  mov     eax, cs:dword_18000E510
0x180004a3b  test    eax, eax
0x180004a3d  jg      short loc_180004A4C
0x180004a3f  xor     eax, eax
0x180004a41  mov     rbx, [rsp+38h+arg_0]
0x180004a46  add     rsp, 30h
0x180004a4a  pop     rdi
0x180004a4b  retn
0x180004a4c  dec     eax
0x180004a4e  mov     cs:dword_18000E510, eax
0x180004a54  call    __scrt_acquire_startup_lock
0x180004a59  mov     bl, al
0x180004a5b  mov     [rsp+38h+var_18], al
0x180004a5f  cmp     cs:__scrt_current_native_startup_state, 2
0x180004a66  jnz     short loc_180004A9E
0x180004a68  call    __scrt_dllmain_uninitialize_c
0x180004a6d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180004a72  call    _RTC_Terminate
0x180004a77  mov     cs:__scrt_current_native_startup_state, 0
0x180004a81  mov     cl, bl
0x180004a83  call    __scrt_release_startup_lock
0x180004a88  xor     edx, edx
0x180004a8a  mov     cl, dil
0x180004a8d  call    __scrt_uninitialize_crt
0x180004a92  movzx   ebx, al
0x180004a95  call    __scrt_dllmain_uninitialize_critical
0x180004a9a  mov     eax, ebx
0x180004a9c  jmp     short loc_180004A41
0x180004a9e  mov     ecx, 7
0x180004aa3  call    __scrt_fastfail
0x1800084b9  push    rbp
0x1800084bb  sub     rsp, 20h
0x1800084bf  mov     rbp, rdx
0x1800084c2  mov     cl, [rbp+20h]
0x1800084c5  call    __scrt_release_startup_lock
0x1800084ca  nop
0x1800084cb  add     rsp, 20h
0x1800084cf  pop     rbp
0x1800084d0  retn
0x1800084d2  push    rbp
0x1800084d4  sub     rsp, 20h
0x1800084d8  mov     rbp, rdx
0x1800084db  add     rsp, 20h
0x1800084df  pop     rbp
0x1800084e0  jmp     __scrt_dllmain_uninitialize_critical
```
