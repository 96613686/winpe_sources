# dllmain_crt_process_detach

- ea: `0x180001298`
- end: `0x18000131b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001140`

## callees

- `0x180001298`
- `0x1800015d0`
- `0x180001608`
- `0x180001730`
- `0x180001768`
- `0x1800018f8`
- `0x180001924`
- `0x180001964`
- `0x1800019b4`

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

  if ( dword_180023CD0 <= 0 )
    return 0;
  --dword_180023CD0;
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
0x180001298  mov     [rsp+arg_0], rbx
0x18000129d  push    rdi
0x18000129e  sub     rsp, 30h
0x1800012a2  mov     dil, cl
0x1800012a5  mov     eax, cs:dword_180023CD0
0x1800012ab  test    eax, eax
0x1800012ad  jg      short loc_1800012BC
0x1800012af  xor     eax, eax
0x1800012b1  mov     rbx, [rsp+38h+arg_0]
0x1800012b6  add     rsp, 30h
0x1800012ba  pop     rdi
0x1800012bb  retn
0x1800012bc  dec     eax
0x1800012be  mov     cs:dword_180023CD0, eax
0x1800012c4  call    __scrt_acquire_startup_lock
0x1800012c9  mov     bl, al
0x1800012cb  mov     [rsp+38h+var_18], al
0x1800012cf  cmp     cs:__scrt_current_native_startup_state, 2
0x1800012d6  jnz     short loc_18000130E
0x1800012d8  call    __scrt_dllmain_uninitialize_c
0x1800012dd  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800012e2  call    _RTC_Terminate
0x1800012e7  mov     cs:__scrt_current_native_startup_state, 0
0x1800012f1  mov     cl, bl
0x1800012f3  call    __scrt_release_startup_lock
0x1800012f8  xor     edx, edx
0x1800012fa  mov     cl, dil
0x1800012fd  call    __scrt_uninitialize_crt
0x180001302  movzx   ebx, al
0x180001305  call    __scrt_dllmain_uninitialize_critical
0x18000130a  mov     eax, ebx
0x18000130c  jmp     short loc_1800012B1
0x18000130e  mov     ecx, 7
0x180001313  call    __scrt_fastfail
0x180016399  push    rbp
0x18001639b  sub     rsp, 20h
0x18001639f  mov     rbp, rdx
0x1800163a2  mov     cl, [rbp+20h]
0x1800163a5  call    __scrt_release_startup_lock
0x1800163aa  nop
0x1800163ab  add     rsp, 20h
0x1800163af  pop     rbp
0x1800163b0  retn
0x1800163b2  push    rbp
0x1800163b4  sub     rsp, 20h
0x1800163b8  mov     rbp, rdx
0x1800163bb  add     rsp, 20h
0x1800163bf  pop     rbp
0x1800163c0  jmp     __scrt_dllmain_uninitialize_critical
```
