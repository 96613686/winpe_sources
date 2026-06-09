# dllmain_crt_process_detach

- ea: `0x180015e78`
- end: `0x180015efb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180015d20`

## callees

- `0x180015e78`
- `0x18001621c`
- `0x180016254`
- `0x18001637c`
- `0x1800163b4`
- `0x180016544`
- `0x180016570`
- `0x1800165b0`
- `0x180016600`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_1800312F0 <= 0 )
    return 0;
  --dword_1800312F0;
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
0x180015e78  mov     [rsp+arg_0], rbx
0x180015e7d  push    rdi
0x180015e7e  sub     rsp, 30h
0x180015e82  mov     dil, cl
0x180015e85  mov     eax, cs:dword_1800312F0
0x180015e8b  test    eax, eax
0x180015e8d  jg      short loc_180015E9C
0x180015e8f  xor     eax, eax
0x180015e91  mov     rbx, [rsp+38h+arg_0]
0x180015e96  add     rsp, 30h
0x180015e9a  pop     rdi
0x180015e9b  retn
0x180015e9c  dec     eax
0x180015e9e  mov     cs:dword_1800312F0, eax
0x180015ea4  call    __scrt_acquire_startup_lock
0x180015ea9  mov     bl, al
0x180015eab  mov     [rsp+38h+var_18], al
0x180015eaf  cmp     cs:__scrt_current_native_startup_state, 2
0x180015eb6  jnz     short loc_180015EEE
0x180015eb8  call    __scrt_dllmain_uninitialize_c
0x180015ebd  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180015ec2  call    _RTC_Terminate
0x180015ec7  mov     cs:__scrt_current_native_startup_state, 0
0x180015ed1  mov     cl, bl
0x180015ed3  call    __scrt_release_startup_lock
0x180015ed8  xor     edx, edx
0x180015eda  mov     cl, dil
0x180015edd  call    __scrt_uninitialize_crt
0x180015ee2  movzx   ebx, al
0x180015ee5  call    __scrt_dllmain_uninitialize_critical
0x180015eea  mov     eax, ebx
0x180015eec  jmp     short loc_180015E91
0x180015eee  mov     ecx, 7
0x180015ef3  call    __scrt_fastfail
0x18002515a  push    rbp
0x18002515c  sub     rsp, 20h
0x180025160  mov     rbp, rdx
0x180025163  mov     cl, [rbp+20h]
0x180025166  call    __scrt_release_startup_lock
0x18002516b  nop
0x18002516c  add     rsp, 20h
0x180025170  pop     rbp
0x180025171  retn
0x180025173  push    rbp
0x180025175  sub     rsp, 20h
0x180025179  mov     rbp, rdx
0x18002517c  add     rsp, 20h
0x180025180  pop     rbp
0x180025181  jmp     __scrt_dllmain_uninitialize_critical
```
