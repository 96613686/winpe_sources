# dllmain_crt_process_detach

- ea: `0x180001ee8`
- end: `0x180001f6b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001d90`

## callees

- `0x180001ee8`
- `0x180002124`
- `0x18000224c`
- `0x180002284`
- `0x180002414`
- `0x180002440`
- `0x180002608`
- `0x180002650`
- `0x1800026a0`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_1800125B0 <= 0 )
    return 0;
  --dword_1800125B0;
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
0x180001ee8  mov     [rsp+arg_0], rbx
0x180001eed  push    rdi
0x180001eee  sub     rsp, 30h
0x180001ef2  mov     dil, cl
0x180001ef5  mov     eax, cs:dword_1800125B0
0x180001efb  test    eax, eax
0x180001efd  jg      short loc_180001F0C
0x180001eff  xor     eax, eax
0x180001f01  mov     rbx, [rsp+38h+arg_0]
0x180001f06  add     rsp, 30h
0x180001f0a  pop     rdi
0x180001f0b  retn
0x180001f0c  dec     eax
0x180001f0e  mov     cs:dword_1800125B0, eax
0x180001f14  call    __scrt_acquire_startup_lock
0x180001f19  mov     bl, al
0x180001f1b  mov     [rsp+38h+var_18], al
0x180001f1f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001f26  jnz     short loc_180001F5E
0x180001f28  call    __scrt_dllmain_uninitialize_c
0x180001f2d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001f32  call    _RTC_Terminate
0x180001f37  mov     cs:__scrt_current_native_startup_state, 0
0x180001f41  mov     cl, bl
0x180001f43  call    __scrt_release_startup_lock
0x180001f48  xor     edx, edx
0x180001f4a  mov     cl, dil
0x180001f4d  call    __scrt_uninitialize_crt
0x180001f52  movzx   ebx, al
0x180001f55  call    __scrt_dllmain_uninitialize_critical
0x180001f5a  mov     eax, ebx
0x180001f5c  jmp     short loc_180001F01
0x180001f5e  mov     ecx, 7
0x180001f63  call    __scrt_fastfail
0x180009161  push    rbp
0x180009163  sub     rsp, 20h
0x180009167  mov     rbp, rdx
0x18000916a  mov     cl, [rbp+20h]
0x18000916d  call    __scrt_release_startup_lock
0x180009172  nop
0x180009173  add     rsp, 20h
0x180009177  pop     rbp
0x180009178  retn
0x18000917a  push    rbp
0x18000917c  sub     rsp, 20h
0x180009180  mov     rbp, rdx
0x180009183  add     rsp, 20h
0x180009187  pop     rbp
0x180009188  jmp     __scrt_dllmain_uninitialize_critical
```
