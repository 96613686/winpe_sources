# dllmain_crt_process_detach

- ea: `0x180001398`
- end: `0x18000141b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001240`

## callees

- `0x180001398`
- `0x18000172c`
- `0x180001764`
- `0x18000188c`
- `0x1800018c4`
- `0x180001a54`
- `0x180001a80`
- `0x180001b20`
- `0x180001b70`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  unsigned int v5; // ebx

  if ( dword_1800101F0 <= 0 )
    return 0;
  --dword_1800101F0;
  v3 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
    _scrt_fastfail(7u);
  _scrt_dllmain_uninitialize_c();
  __scrt_uninitialize_type_info();
  RTC_Terminate();
  _scrt_current_native_startup_state = 0;
  _scrt_release_startup_lock(v3);
  LOBYTE(v4) = a1;
  v5 = (unsigned __int8)_scrt_uninitialize_crt(v4, 0);
  _scrt_dllmain_uninitialize_critical();
  return v5;
}

```

## disassembly

```asm
0x180001398  mov     [rsp+arg_0], rbx
0x18000139d  push    rdi
0x18000139e  sub     rsp, 30h
0x1800013a2  mov     dil, cl
0x1800013a5  mov     eax, cs:dword_1800101F0
0x1800013ab  test    eax, eax
0x1800013ad  jg      short loc_1800013BC
0x1800013af  xor     eax, eax
0x1800013b1  mov     rbx, [rsp+38h+arg_0]
0x1800013b6  add     rsp, 30h
0x1800013ba  pop     rdi
0x1800013bb  retn
0x1800013bc  dec     eax
0x1800013be  mov     cs:dword_1800101F0, eax
0x1800013c4  call    __scrt_acquire_startup_lock
0x1800013c9  mov     bl, al
0x1800013cb  mov     [rsp+38h+var_18], al
0x1800013cf  cmp     cs:__scrt_current_native_startup_state, 2
0x1800013d6  jnz     short loc_18000140E
0x1800013d8  call    __scrt_dllmain_uninitialize_c
0x1800013dd  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800013e2  call    _RTC_Terminate
0x1800013e7  mov     cs:__scrt_current_native_startup_state, 0
0x1800013f1  mov     cl, bl
0x1800013f3  call    __scrt_release_startup_lock
0x1800013f8  xor     edx, edx
0x1800013fa  mov     cl, dil
0x1800013fd  call    __scrt_uninitialize_crt
0x180001402  movzx   ebx, al
0x180001405  call    __scrt_dllmain_uninitialize_critical
0x18000140a  mov     eax, ebx
0x18000140c  jmp     short loc_1800013B1
0x18000140e  mov     ecx, 7
0x180001413  call    __scrt_fastfail
0x1800095e9  push    rbp
0x1800095eb  sub     rsp, 20h
0x1800095ef  mov     rbp, rdx
0x1800095f2  mov     cl, [rbp+20h]
0x1800095f5  call    __scrt_release_startup_lock
0x1800095fa  nop
0x1800095fb  add     rsp, 20h
0x1800095ff  pop     rbp
0x180009600  retn
0x180009602  push    rbp
0x180009604  sub     rsp, 20h
0x180009608  mov     rbp, rdx
0x18000960b  add     rsp, 20h
0x18000960f  pop     rbp
0x180009610  jmp     __scrt_dllmain_uninitialize_critical
```
