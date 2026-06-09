# dllmain_crt_process_detach

- ea: `0x18001dfa8`
- end: `0x18001e02b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18001de50`

## callees

- `0x18001dfa8`
- `0x18001e1f4`
- `0x18001e31c`
- `0x18001e354`
- `0x18001e4e4`
- `0x18001e510`
- `0x18001e6ac`
- `0x18001e6f4`
- `0x18001e744`

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

  if ( dword_18003C490 <= 0 )
    return 0;
  --dword_18003C490;
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
0x18001dfa8  mov     [rsp+arg_0], rbx
0x18001dfad  push    rdi
0x18001dfae  sub     rsp, 30h
0x18001dfb2  mov     dil, cl
0x18001dfb5  mov     eax, cs:dword_18003C490
0x18001dfbb  test    eax, eax
0x18001dfbd  jg      short loc_18001DFCC
0x18001dfbf  xor     eax, eax
0x18001dfc1  mov     rbx, [rsp+38h+arg_0]
0x18001dfc6  add     rsp, 30h
0x18001dfca  pop     rdi
0x18001dfcb  retn
0x18001dfcc  dec     eax
0x18001dfce  mov     cs:dword_18003C490, eax
0x18001dfd4  call    __scrt_acquire_startup_lock
0x18001dfd9  mov     bl, al
0x18001dfdb  mov     [rsp+38h+var_18], al
0x18001dfdf  cmp     cs:__scrt_current_native_startup_state, 2
0x18001dfe6  jnz     short loc_18001E01E
0x18001dfe8  call    __scrt_dllmain_uninitialize_c
0x18001dfed  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x18001dff2  call    _RTC_Terminate
0x18001dff7  mov     cs:__scrt_current_native_startup_state, 0
0x18001e001  mov     cl, bl
0x18001e003  call    __scrt_release_startup_lock
0x18001e008  xor     edx, edx
0x18001e00a  mov     cl, dil
0x18001e00d  call    __scrt_uninitialize_crt
0x18001e012  movzx   ebx, al
0x18001e015  call    __scrt_dllmain_uninitialize_critical
0x18001e01a  mov     eax, ebx
0x18001e01c  jmp     short loc_18001DFC1
0x18001e01e  mov     ecx, 7
0x18001e023  call    __scrt_fastfail
0x18002f71d  push    rbp
0x18002f71f  sub     rsp, 20h
0x18002f723  mov     rbp, rdx
0x18002f726  mov     cl, [rbp+20h]
0x18002f729  call    __scrt_release_startup_lock
0x18002f72e  nop
0x18002f72f  add     rsp, 20h
0x18002f733  pop     rbp
0x18002f734  retn
0x18002f736  push    rbp
0x18002f738  sub     rsp, 20h
0x18002f73c  mov     rbp, rdx
0x18002f73f  add     rsp, 20h
0x18002f743  pop     rbp
0x18002f744  jmp     __scrt_dllmain_uninitialize_critical
```
