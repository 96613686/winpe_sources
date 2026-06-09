# dllmain_crt_process_detach

- ea: `0x180001398`
- end: `0x18000141b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001240`

## callees

- `0x180001398`
- `0x1800015d4`
- `0x1800016fc`
- `0x180001734`
- `0x1800018c4`
- `0x1800018f0`
- `0x180001b24`
- `0x180001b6c`
- `0x180001bbc`

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

  if ( dword_180023350 <= 0 )
    return 0;
  --dword_180023350;
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
0x180001398  mov     [rsp+arg_0], rbx
0x18000139d  push    rdi
0x18000139e  sub     rsp, 30h
0x1800013a2  mov     dil, cl
0x1800013a5  mov     eax, cs:dword_180023350
0x1800013ab  test    eax, eax
0x1800013ad  jg      short loc_1800013BC
0x1800013af  xor     eax, eax
0x1800013b1  mov     rbx, [rsp+38h+arg_0]
0x1800013b6  add     rsp, 30h
0x1800013ba  pop     rdi
0x1800013bb  retn
0x1800013bc  dec     eax
0x1800013be  mov     cs:dword_180023350, eax
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
0x180018da9  push    rbp
0x180018dab  sub     rsp, 20h
0x180018daf  mov     rbp, rdx
0x180018db2  mov     cl, [rbp+20h]
0x180018db5  call    __scrt_release_startup_lock
0x180018dba  nop
0x180018dbb  add     rsp, 20h
0x180018dbf  pop     rbp
0x180018dc0  retn
0x180018dc2  push    rbp
0x180018dc4  sub     rsp, 20h
0x180018dc8  mov     rbp, rdx
0x180018dcb  add     rsp, 20h
0x180018dcf  pop     rbp
0x180018dd0  jmp     __scrt_dllmain_uninitialize_critical
```
