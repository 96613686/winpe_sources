# dllmain_crt_process_detach

- ea: `0x180001428`
- end: `0x1800014ab`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800012d0`

## callees

- `0x180001428`
- `0x180001734`
- `0x18000176c`
- `0x180001894`
- `0x1800018cc`
- `0x180001a5c`
- `0x180001a88`
- `0x180001b28`
- `0x180001b78`

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

  if ( dword_180035610 <= 0 )
    return 0;
  --dword_180035610;
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
0x180001428  mov     [rsp+arg_0], rbx
0x18000142d  push    rdi
0x18000142e  sub     rsp, 30h
0x180001432  mov     dil, cl
0x180001435  mov     eax, cs:dword_180035610
0x18000143b  test    eax, eax
0x18000143d  jg      short loc_18000144C
0x18000143f  xor     eax, eax
0x180001441  mov     rbx, [rsp+38h+arg_0]
0x180001446  add     rsp, 30h
0x18000144a  pop     rdi
0x18000144b  retn
0x18000144c  dec     eax
0x18000144e  mov     cs:dword_180035610, eax
0x180001454  call    __scrt_acquire_startup_lock
0x180001459  mov     bl, al
0x18000145b  mov     [rsp+38h+var_18], al
0x18000145f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001466  jnz     short loc_18000149E
0x180001468  call    __scrt_dllmain_uninitialize_c
0x18000146d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001472  call    _RTC_Terminate
0x180001477  mov     cs:__scrt_current_native_startup_state, 0
0x180001481  mov     cl, bl
0x180001483  call    __scrt_release_startup_lock
0x180001488  xor     edx, edx
0x18000148a  mov     cl, dil
0x18000148d  call    __scrt_uninitialize_crt
0x180001492  movzx   ebx, al
0x180001495  call    __scrt_dllmain_uninitialize_critical
0x18000149a  mov     eax, ebx
0x18000149c  jmp     short loc_180001441
0x18000149e  mov     ecx, 7
0x1800014a3  call    __scrt_fastfail
0x180025409  push    rbp
0x18002540b  sub     rsp, 20h
0x18002540f  mov     rbp, rdx
0x180025412  mov     cl, [rbp+20h]
0x180025415  call    __scrt_release_startup_lock
0x18002541a  nop
0x18002541b  add     rsp, 20h
0x18002541f  pop     rbp
0x180025420  retn
0x180025422  push    rbp
0x180025424  sub     rsp, 20h
0x180025428  mov     rbp, rdx
0x18002542b  add     rsp, 20h
0x18002542f  pop     rbp
0x180025430  jmp     __scrt_dllmain_uninitialize_critical
```
