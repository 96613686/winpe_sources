# dllmain_crt_process_detach

- ea: `0x180001998`
- end: `0x180001a1b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001840`

## callees

- `0x180001998`
- `0x180001c7c`
- `0x180001da4`
- `0x180001ddc`
- `0x180001f6c`
- `0x180001f98`
- `0x1800021f8`
- `0x180002240`
- `0x180002290`

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

  if ( dword_18003DD90 <= 0 )
    return 0;
  --dword_18003DD90;
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
0x180001998  mov     [rsp+arg_0], rbx
0x18000199d  push    rdi
0x18000199e  sub     rsp, 30h
0x1800019a2  mov     dil, cl
0x1800019a5  mov     eax, cs:dword_18003DD90
0x1800019ab  test    eax, eax
0x1800019ad  jg      short loc_1800019BC
0x1800019af  xor     eax, eax
0x1800019b1  mov     rbx, [rsp+38h+arg_0]
0x1800019b6  add     rsp, 30h
0x1800019ba  pop     rdi
0x1800019bb  retn
0x1800019bc  dec     eax
0x1800019be  mov     cs:dword_18003DD90, eax
0x1800019c4  call    __scrt_acquire_startup_lock
0x1800019c9  mov     bl, al
0x1800019cb  mov     [rsp+38h+var_18], al
0x1800019cf  cmp     cs:__scrt_current_native_startup_state, 2
0x1800019d6  jnz     short loc_180001A0E
0x1800019d8  call    __scrt_dllmain_uninitialize_c
0x1800019dd  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800019e2  call    _RTC_Terminate
0x1800019e7  mov     cs:__scrt_current_native_startup_state, 0
0x1800019f1  mov     cl, bl
0x1800019f3  call    __scrt_release_startup_lock
0x1800019f8  xor     edx, edx
0x1800019fa  mov     cl, dil
0x1800019fd  call    __scrt_uninitialize_crt
0x180001a02  movzx   ebx, al
0x180001a05  call    __scrt_dllmain_uninitialize_critical
0x180001a0a  mov     eax, ebx
0x180001a0c  jmp     short loc_1800019B1
0x180001a0e  mov     ecx, 7
0x180001a13  call    __scrt_fastfail
0x18002c2d9  push    rbp
0x18002c2db  sub     rsp, 20h
0x18002c2df  mov     rbp, rdx
0x18002c2e2  mov     cl, [rbp+20h]
0x18002c2e5  call    __scrt_release_startup_lock
0x18002c2ea  nop
0x18002c2eb  add     rsp, 20h
0x18002c2ef  pop     rbp
0x18002c2f0  retn
0x18002c2f2  push    rbp
0x18002c2f4  sub     rsp, 20h
0x18002c2f8  mov     rbp, rdx
0x18002c2fb  add     rsp, 20h
0x18002c2ff  pop     rbp
0x18002c300  jmp     __scrt_dllmain_uninitialize_critical
```
