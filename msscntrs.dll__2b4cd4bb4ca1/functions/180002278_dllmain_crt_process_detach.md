# dllmain_crt_process_detach

- ea: `0x180002278`
- end: `0x1800022fb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180002120`

## callees

- `0x180002278`
- `0x1800025d8`
- `0x180002700`
- `0x180002738`
- `0x1800028c8`
- `0x1800028f4`
- `0x180002e30`
- `0x180002e78`
- `0x180002ec8`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_180021D50 <= 0 )
    return 0;
  --dword_180021D50;
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
0x180002278  mov     [rsp+arg_0], rbx
0x18000227d  push    rdi
0x18000227e  sub     rsp, 30h
0x180002282  mov     dil, cl
0x180002285  mov     eax, cs:dword_180021D50
0x18000228b  test    eax, eax
0x18000228d  jg      short loc_18000229C
0x18000228f  xor     eax, eax
0x180002291  mov     rbx, [rsp+38h+arg_0]
0x180002296  add     rsp, 30h
0x18000229a  pop     rdi
0x18000229b  retn
0x18000229c  dec     eax
0x18000229e  mov     cs:dword_180021D50, eax
0x1800022a4  call    __scrt_acquire_startup_lock
0x1800022a9  mov     bl, al
0x1800022ab  mov     [rsp+38h+var_18], al
0x1800022af  cmp     cs:__scrt_current_native_startup_state, 2
0x1800022b6  jnz     short loc_1800022EE
0x1800022b8  call    __scrt_dllmain_uninitialize_c
0x1800022bd  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800022c2  call    _RTC_Terminate
0x1800022c7  mov     cs:__scrt_current_native_startup_state, 0
0x1800022d1  mov     cl, bl
0x1800022d3  call    __scrt_release_startup_lock
0x1800022d8  xor     edx, edx
0x1800022da  mov     cl, dil
0x1800022dd  call    __scrt_uninitialize_crt
0x1800022e2  movzx   ebx, al
0x1800022e5  call    __scrt_dllmain_uninitialize_critical
0x1800022ea  mov     eax, ebx
0x1800022ec  jmp     short loc_180002291
0x1800022ee  mov     ecx, 7
0x1800022f3  call    __scrt_fastfail
0x180015769  push    rbp
0x18001576b  sub     rsp, 20h
0x18001576f  mov     rbp, rdx
0x180015772  mov     cl, [rbp+20h]
0x180015775  call    __scrt_release_startup_lock
0x18001577a  nop
0x18001577b  add     rsp, 20h
0x18001577f  pop     rbp
0x180015780  retn
0x180015782  push    rbp
0x180015784  sub     rsp, 20h
0x180015788  mov     rbp, rdx
0x18001578b  add     rsp, 20h
0x18001578f  pop     rbp
0x180015790  jmp     __scrt_dllmain_uninitialize_critical
```
