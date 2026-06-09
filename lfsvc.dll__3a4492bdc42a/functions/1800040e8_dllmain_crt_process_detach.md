# dllmain_crt_process_detach

- ea: `0x1800040e8`
- end: `0x18000416b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180003f90`

## callees

- `0x1800040e8`
- `0x180004378`
- `0x1800044a0`
- `0x1800044d8`
- `0x180004668`
- `0x180004694`
- `0x18000482c`
- `0x180004874`
- `0x1800048c4`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_1800122D0 <= 0 )
    return 0;
  --dword_1800122D0;
  v3 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
    _scrt_fastfail(7);
  _scrt_dllmain_uninitialize_c();
  __scrt_uninitialize_type_info();
  RTC_Terminate();
  _scrt_current_native_startup_state = 0;
  LOBYTE(v4) = v3;
  _scrt_release_startup_lock(v4);
  LOBYTE(v5) = a1;
  v6 = (unsigned __int8)_scrt_uninitialize_crt(v5, 0);
  _scrt_dllmain_uninitialize_critical();
  return v6;
}

```

## disassembly

```asm
0x1800040e8  mov     [rsp+arg_0], rbx
0x1800040ed  push    rdi
0x1800040ee  sub     rsp, 30h
0x1800040f2  mov     dil, cl
0x1800040f5  mov     eax, cs:dword_1800122D0
0x1800040fb  test    eax, eax
0x1800040fd  jg      short loc_18000410C
0x1800040ff  xor     eax, eax
0x180004101  mov     rbx, [rsp+38h+arg_0]
0x180004106  add     rsp, 30h
0x18000410a  pop     rdi
0x18000410b  retn
0x18000410c  dec     eax
0x18000410e  mov     cs:dword_1800122D0, eax
0x180004114  call    __scrt_acquire_startup_lock
0x180004119  mov     bl, al
0x18000411b  mov     [rsp+38h+var_18], al
0x18000411f  cmp     cs:__scrt_current_native_startup_state, 2
0x180004126  jnz     short loc_18000415E
0x180004128  call    __scrt_dllmain_uninitialize_c
0x18000412d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180004132  call    _RTC_Terminate
0x180004137  mov     cs:__scrt_current_native_startup_state, 0
0x180004141  mov     cl, bl
0x180004143  call    __scrt_release_startup_lock
0x180004148  xor     edx, edx
0x18000414a  mov     cl, dil
0x18000414d  call    __scrt_uninitialize_crt
0x180004152  movzx   ebx, al
0x180004155  call    __scrt_dllmain_uninitialize_critical
0x18000415a  mov     eax, ebx
0x18000415c  jmp     short loc_180004101
0x18000415e  mov     ecx, 7
0x180004163  call    __scrt_fastfail
0x18000b4a5  push    rbp
0x18000b4a7  sub     rsp, 20h
0x18000b4ab  mov     rbp, rdx
0x18000b4ae  mov     cl, [rbp+20h]
0x18000b4b1  call    __scrt_release_startup_lock
0x18000b4b6  nop
0x18000b4b7  add     rsp, 20h
0x18000b4bb  pop     rbp
0x18000b4bc  retn
0x18000b4be  push    rbp
0x18000b4c0  sub     rsp, 20h
0x18000b4c4  mov     rbp, rdx
0x18000b4c7  add     rsp, 20h
0x18000b4cb  pop     rbp
0x18000b4cc  jmp     __scrt_dllmain_uninitialize_critical
```
