# dllmain_crt_process_detach

- ea: `0x1800020c8`
- end: `0x18000214b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001f70`

## callees

- `0x1800020c8`
- `0x180002304`
- `0x18000242c`
- `0x180002464`
- `0x1800025f4`
- `0x180002620`
- `0x1800027bc`
- `0x180002804`
- `0x180002854`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_18002B550 <= 0 )
    return 0;
  --dword_18002B550;
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
0x1800020c8  mov     [rsp+arg_0], rbx
0x1800020cd  push    rdi
0x1800020ce  sub     rsp, 30h
0x1800020d2  mov     dil, cl
0x1800020d5  mov     eax, cs:dword_18002B550
0x1800020db  test    eax, eax
0x1800020dd  jg      short loc_1800020EC
0x1800020df  xor     eax, eax
0x1800020e1  mov     rbx, [rsp+38h+arg_0]
0x1800020e6  add     rsp, 30h
0x1800020ea  pop     rdi
0x1800020eb  retn
0x1800020ec  dec     eax
0x1800020ee  mov     cs:dword_18002B550, eax
0x1800020f4  call    __scrt_acquire_startup_lock
0x1800020f9  mov     bl, al
0x1800020fb  mov     [rsp+38h+var_18], al
0x1800020ff  cmp     cs:__scrt_current_native_startup_state, 2
0x180002106  jnz     short loc_18000213E
0x180002108  call    __scrt_dllmain_uninitialize_c
0x18000210d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180002112  call    _RTC_Terminate
0x180002117  mov     cs:__scrt_current_native_startup_state, 0
0x180002121  mov     cl, bl
0x180002123  call    __scrt_release_startup_lock
0x180002128  xor     edx, edx
0x18000212a  mov     cl, dil
0x18000212d  call    __scrt_uninitialize_crt
0x180002132  movzx   ebx, al
0x180002135  call    __scrt_dllmain_uninitialize_critical
0x18000213a  mov     eax, ebx
0x18000213c  jmp     short loc_1800020E1
0x18000213e  mov     ecx, 7
0x180002143  call    __scrt_fastfail
0x18001eae9  push    rbp
0x18001eaeb  sub     rsp, 20h
0x18001eaef  mov     rbp, rdx
0x18001eaf2  mov     cl, [rbp+20h]
0x18001eaf5  call    __scrt_release_startup_lock
0x18001eafa  nop
0x18001eafb  add     rsp, 20h
0x18001eaff  pop     rbp
0x18001eb00  retn
0x18001eb02  push    rbp
0x18001eb04  sub     rsp, 20h
0x18001eb08  mov     rbp, rdx
0x18001eb0b  add     rsp, 20h
0x18001eb0f  pop     rbp
0x18001eb10  jmp     __scrt_dllmain_uninitialize_critical
```
