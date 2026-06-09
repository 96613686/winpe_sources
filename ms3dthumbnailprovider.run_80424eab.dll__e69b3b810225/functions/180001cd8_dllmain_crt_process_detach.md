# dllmain_crt_process_detach

- ea: `0x180001cd8`
- end: `0x180001d5b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001b80`

## callees

- `0x180001cd8`
- `0x180001f50`
- `0x180002078`
- `0x1800020b0`
- `0x180002240`
- `0x18000226c`
- `0x1800023cc`
- `0x180002414`
- `0x180002464`

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

  if ( dword_180010230 <= 0 )
    return 0;
  --dword_180010230;
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
0x180001cd8  mov     [rsp+arg_0], rbx
0x180001cdd  push    rdi
0x180001cde  sub     rsp, 30h
0x180001ce2  mov     dil, cl
0x180001ce5  mov     eax, cs:dword_180010230
0x180001ceb  test    eax, eax
0x180001ced  jg      short loc_180001CFC
0x180001cef  xor     eax, eax
0x180001cf1  mov     rbx, [rsp+38h+arg_0]
0x180001cf6  add     rsp, 30h
0x180001cfa  pop     rdi
0x180001cfb  retn
0x180001cfc  dec     eax
0x180001cfe  mov     cs:dword_180010230, eax
0x180001d04  call    __scrt_acquire_startup_lock
0x180001d09  mov     bl, al
0x180001d0b  mov     [rsp+38h+var_18], al
0x180001d0f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001d16  jnz     short loc_180001D4E
0x180001d18  call    __scrt_dllmain_uninitialize_c
0x180001d1d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001d22  call    _RTC_Terminate
0x180001d27  mov     cs:__scrt_current_native_startup_state, 0
0x180001d31  mov     cl, bl
0x180001d33  call    __scrt_release_startup_lock
0x180001d38  xor     edx, edx
0x180001d3a  mov     cl, dil
0x180001d3d  call    __scrt_uninitialize_crt
0x180001d42  movzx   ebx, al
0x180001d45  call    __scrt_dllmain_uninitialize_critical
0x180001d4a  mov     eax, ebx
0x180001d4c  jmp     short loc_180001CF1
0x180001d4e  mov     ecx, 7
0x180001d53  call    __scrt_fastfail
0x18000a379  push    rbp
0x18000a37b  sub     rsp, 20h
0x18000a37f  mov     rbp, rdx
0x18000a382  mov     cl, [rbp+20h]
0x18000a385  call    __scrt_release_startup_lock
0x18000a38a  nop
0x18000a38b  add     rsp, 20h
0x18000a38f  pop     rbp
0x18000a390  retn
0x18000a392  push    rbp
0x18000a394  sub     rsp, 20h
0x18000a398  mov     rbp, rdx
0x18000a39b  add     rsp, 20h
0x18000a39f  pop     rbp
0x18000a3a0  jmp     __scrt_dllmain_uninitialize_critical
```
