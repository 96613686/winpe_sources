# dllmain_crt_process_detach

- ea: `0x180001368`
- end: `0x1800013eb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001210`

## callees

- `0x180001368`
- `0x180001674`
- `0x1800016ac`
- `0x1800017d4`
- `0x18000180c`
- `0x18000199c`
- `0x1800019c8`
- `0x180001a68`
- `0x180001ab8`

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

  if ( dword_180024750 <= 0 )
    return 0;
  --dword_180024750;
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
0x180001368  mov     [rsp+arg_0], rbx
0x18000136d  push    rdi
0x18000136e  sub     rsp, 30h
0x180001372  mov     dil, cl
0x180001375  mov     eax, cs:dword_180024750
0x18000137b  test    eax, eax
0x18000137d  jg      short loc_18000138C
0x18000137f  xor     eax, eax
0x180001381  mov     rbx, [rsp+38h+arg_0]
0x180001386  add     rsp, 30h
0x18000138a  pop     rdi
0x18000138b  retn
0x18000138c  dec     eax
0x18000138e  mov     cs:dword_180024750, eax
0x180001394  call    __scrt_acquire_startup_lock
0x180001399  mov     bl, al
0x18000139b  mov     [rsp+38h+var_18], al
0x18000139f  cmp     cs:__scrt_current_native_startup_state, 2
0x1800013a6  jnz     short loc_1800013DE
0x1800013a8  call    __scrt_dllmain_uninitialize_c
0x1800013ad  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800013b2  call    _RTC_Terminate
0x1800013b7  mov     cs:__scrt_current_native_startup_state, 0
0x1800013c1  mov     cl, bl
0x1800013c3  call    __scrt_release_startup_lock
0x1800013c8  xor     edx, edx
0x1800013ca  mov     cl, dil
0x1800013cd  call    __scrt_uninitialize_crt
0x1800013d2  movzx   ebx, al
0x1800013d5  call    __scrt_dllmain_uninitialize_critical
0x1800013da  mov     eax, ebx
0x1800013dc  jmp     short loc_180001381
0x1800013de  mov     ecx, 7
0x1800013e3  call    __scrt_fastfail
0x18001d3f9  push    rbp
0x18001d3fb  sub     rsp, 20h
0x18001d3ff  mov     rbp, rdx
0x18001d402  mov     cl, [rbp+20h]
0x18001d405  call    __scrt_release_startup_lock
0x18001d40a  nop
0x18001d40b  add     rsp, 20h
0x18001d40f  pop     rbp
0x18001d410  retn
0x18001d412  push    rbp
0x18001d414  sub     rsp, 20h
0x18001d418  mov     rbp, rdx
0x18001d41b  add     rsp, 20h
0x18001d41f  pop     rbp
0x18001d420  jmp     __scrt_dllmain_uninitialize_critical
```
