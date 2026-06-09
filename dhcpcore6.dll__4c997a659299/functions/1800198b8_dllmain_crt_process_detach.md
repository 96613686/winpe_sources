# dllmain_crt_process_detach

- ea: `0x1800198b8`
- end: `0x18001993b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180019760`

## callees

- `0x1800198b8`
- `0x180019bf0`
- `0x180019c28`
- `0x180019d50`
- `0x180019d88`
- `0x180019f18`
- `0x180019f44`
- `0x180019fe4`
- `0x18001a034`

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

  if ( dword_1800422A0 <= 0 )
    return 0;
  --dword_1800422A0;
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
0x1800198b8  mov     [rsp+arg_0], rbx
0x1800198bd  push    rdi
0x1800198be  sub     rsp, 30h
0x1800198c2  mov     dil, cl
0x1800198c5  mov     eax, cs:dword_1800422A0
0x1800198cb  test    eax, eax
0x1800198cd  jg      short loc_1800198DC
0x1800198cf  xor     eax, eax
0x1800198d1  mov     rbx, [rsp+38h+arg_0]
0x1800198d6  add     rsp, 30h
0x1800198da  pop     rdi
0x1800198db  retn
0x1800198dc  dec     eax
0x1800198de  mov     cs:dword_1800422A0, eax
0x1800198e4  call    __scrt_acquire_startup_lock
0x1800198e9  mov     bl, al
0x1800198eb  mov     [rsp+38h+var_18], al
0x1800198ef  cmp     cs:__scrt_current_native_startup_state, 2
0x1800198f6  jnz     short loc_18001992E
0x1800198f8  call    __scrt_dllmain_uninitialize_c
0x1800198fd  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180019902  call    _RTC_Terminate
0x180019907  mov     cs:__scrt_current_native_startup_state, 0
0x180019911  mov     cl, bl
0x180019913  call    __scrt_release_startup_lock
0x180019918  xor     edx, edx
0x18001991a  mov     cl, dil
0x18001991d  call    __scrt_uninitialize_crt
0x180019922  movzx   ebx, al
0x180019925  call    __scrt_dllmain_uninitialize_critical
0x18001992a  mov     eax, ebx
0x18001992c  jmp     short loc_1800198D1
0x18001992e  mov     ecx, 7
0x180019933  call    __scrt_fastfail
0x180030a79  push    rbp
0x180030a7b  sub     rsp, 20h
0x180030a7f  mov     rbp, rdx
0x180030a82  mov     cl, [rbp+20h]
0x180030a85  call    __scrt_release_startup_lock
0x180030a8a  nop
0x180030a8b  add     rsp, 20h
0x180030a8f  pop     rbp
0x180030a90  retn
0x180030a92  push    rbp
0x180030a94  sub     rsp, 20h
0x180030a98  mov     rbp, rdx
0x180030a9b  add     rsp, 20h
0x180030a9f  pop     rbp
0x180030aa0  jmp     __scrt_dllmain_uninitialize_critical
```
