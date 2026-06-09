# dllmain_crt_process_detach

- ea: `0x180001888`
- end: `0x18000190b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001730`

## callees

- `0x180001888`
- `0x180001b94`
- `0x180001bcc`
- `0x180001cf4`
- `0x180001d2c`
- `0x180001ebc`
- `0x180001ee8`
- `0x180001f28`
- `0x180001f78`

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

  if ( dword_18002A810 <= 0 )
    return 0;
  --dword_18002A810;
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
0x180001888  mov     [rsp+arg_0], rbx
0x18000188d  push    rdi
0x18000188e  sub     rsp, 30h
0x180001892  mov     dil, cl
0x180001895  mov     eax, cs:dword_18002A810
0x18000189b  test    eax, eax
0x18000189d  jg      short loc_1800018AC
0x18000189f  xor     eax, eax
0x1800018a1  mov     rbx, [rsp+38h+arg_0]
0x1800018a6  add     rsp, 30h
0x1800018aa  pop     rdi
0x1800018ab  retn
0x1800018ac  dec     eax
0x1800018ae  mov     cs:dword_18002A810, eax
0x1800018b4  call    __scrt_acquire_startup_lock
0x1800018b9  mov     bl, al
0x1800018bb  mov     [rsp+38h+var_18], al
0x1800018bf  cmp     cs:__scrt_current_native_startup_state, 2
0x1800018c6  jnz     short loc_1800018FE
0x1800018c8  call    __scrt_dllmain_uninitialize_c
0x1800018cd  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800018d2  call    _RTC_Terminate
0x1800018d7  mov     cs:__scrt_current_native_startup_state, 0
0x1800018e1  mov     cl, bl
0x1800018e3  call    __scrt_release_startup_lock
0x1800018e8  xor     edx, edx
0x1800018ea  mov     cl, dil
0x1800018ed  call    __scrt_uninitialize_crt
0x1800018f2  movzx   ebx, al
0x1800018f5  call    __scrt_dllmain_uninitialize_critical
0x1800018fa  mov     eax, ebx
0x1800018fc  jmp     short loc_1800018A1
0x1800018fe  mov     ecx, 7
0x180001903  call    __scrt_fastfail
0x18001d149  push    rbp
0x18001d14b  sub     rsp, 20h
0x18001d14f  mov     rbp, rdx
0x18001d152  mov     cl, [rbp+20h]
0x18001d155  call    __scrt_release_startup_lock
0x18001d15a  nop
0x18001d15b  add     rsp, 20h
0x18001d15f  pop     rbp
0x18001d160  retn
0x18001d162  push    rbp
0x18001d164  sub     rsp, 20h
0x18001d168  mov     rbp, rdx
0x18001d16b  add     rsp, 20h
0x18001d16f  pop     rbp
0x18001d170  jmp     __scrt_dllmain_uninitialize_critical
```
