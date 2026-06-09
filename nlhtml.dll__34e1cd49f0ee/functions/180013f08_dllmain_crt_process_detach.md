# dllmain_crt_process_detach

- ea: `0x180013f08`
- end: `0x180013f8b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180013db0`

## callees

- `0x180013f08`
- `0x180014198`
- `0x1800142c0`
- `0x1800142f8`
- `0x180014488`
- `0x1800144b4`
- `0x180014ab0`
- `0x180014af8`
- `0x180014b48`

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

  if ( dword_18003DF10 <= 0 )
    return 0;
  --dword_18003DF10;
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
0x180013f08  mov     [rsp+arg_0], rbx
0x180013f0d  push    rdi
0x180013f0e  sub     rsp, 30h
0x180013f12  mov     dil, cl
0x180013f15  mov     eax, cs:dword_18003DF10
0x180013f1b  test    eax, eax
0x180013f1d  jg      short loc_180013F2C
0x180013f1f  xor     eax, eax
0x180013f21  mov     rbx, [rsp+38h+arg_0]
0x180013f26  add     rsp, 30h
0x180013f2a  pop     rdi
0x180013f2b  retn
0x180013f2c  dec     eax
0x180013f2e  mov     cs:dword_18003DF10, eax
0x180013f34  call    __scrt_acquire_startup_lock
0x180013f39  mov     bl, al
0x180013f3b  mov     [rsp+38h+var_18], al
0x180013f3f  cmp     cs:__scrt_current_native_startup_state, 2
0x180013f46  jnz     short loc_180013F7E
0x180013f48  call    __scrt_dllmain_uninitialize_c
0x180013f4d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180013f52  call    _RTC_Terminate
0x180013f57  mov     cs:__scrt_current_native_startup_state, 0
0x180013f61  mov     cl, bl
0x180013f63  call    __scrt_release_startup_lock
0x180013f68  xor     edx, edx
0x180013f6a  mov     cl, dil
0x180013f6d  call    __scrt_uninitialize_crt
0x180013f72  movzx   ebx, al
0x180013f75  call    __scrt_dllmain_uninitialize_critical
0x180013f7a  mov     eax, ebx
0x180013f7c  jmp     short loc_180013F21
0x180013f7e  mov     ecx, 7
0x180013f83  call    __scrt_fastfail
0x180023a9e  push    rbp
0x180023aa0  sub     rsp, 20h
0x180023aa4  mov     rbp, rdx
0x180023aa7  mov     cl, [rbp+20h]
0x180023aaa  call    __scrt_release_startup_lock
0x180023aaf  nop
0x180023ab0  add     rsp, 20h
0x180023ab4  pop     rbp
0x180023ab5  retn
0x180023ab7  push    rbp
0x180023ab9  sub     rsp, 20h
0x180023abd  mov     rbp, rdx
0x180023ac0  add     rsp, 20h
0x180023ac4  pop     rbp
0x180023ac5  jmp     __scrt_dllmain_uninitialize_critical
```
