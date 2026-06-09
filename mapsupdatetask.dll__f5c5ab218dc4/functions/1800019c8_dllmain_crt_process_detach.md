# dllmain_crt_process_detach

- ea: `0x1800019c8`
- end: `0x180001a4b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001870`

## callees

- `0x1800019c8`
- `0x180001c48`
- `0x180001d70`
- `0x180001da8`
- `0x180001f38`
- `0x180001f64`
- `0x1800020fc`
- `0x180002144`
- `0x180002194`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  unsigned int v5; // ebx

  if ( dword_18000E230 <= 0 )
    return 0;
  --dword_18000E230;
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
0x1800019c8  mov     [rsp+arg_0], rbx
0x1800019cd  push    rdi
0x1800019ce  sub     rsp, 30h
0x1800019d2  mov     dil, cl
0x1800019d5  mov     eax, cs:dword_18000E230
0x1800019db  test    eax, eax
0x1800019dd  jg      short loc_1800019EC
0x1800019df  xor     eax, eax
0x1800019e1  mov     rbx, [rsp+38h+arg_0]
0x1800019e6  add     rsp, 30h
0x1800019ea  pop     rdi
0x1800019eb  retn
0x1800019ec  dec     eax
0x1800019ee  mov     cs:dword_18000E230, eax
0x1800019f4  call    __scrt_acquire_startup_lock
0x1800019f9  mov     bl, al
0x1800019fb  mov     [rsp+38h+var_18], al
0x1800019ff  cmp     cs:__scrt_current_native_startup_state, 2
0x180001a06  jnz     short loc_180001A3E
0x180001a08  call    __scrt_dllmain_uninitialize_c
0x180001a0d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001a12  call    _RTC_Terminate
0x180001a17  mov     cs:__scrt_current_native_startup_state, 0
0x180001a21  mov     cl, bl
0x180001a23  call    __scrt_release_startup_lock
0x180001a28  xor     edx, edx
0x180001a2a  mov     cl, dil
0x180001a2d  call    __scrt_uninitialize_crt
0x180001a32  movzx   ebx, al
0x180001a35  call    __scrt_dllmain_uninitialize_critical
0x180001a3a  mov     eax, ebx
0x180001a3c  jmp     short loc_1800019E1
0x180001a3e  mov     ecx, 7
0x180001a43  call    __scrt_fastfail
0x180007f59  push    rbp
0x180007f5b  sub     rsp, 20h
0x180007f5f  mov     rbp, rdx
0x180007f62  mov     cl, [rbp+20h]
0x180007f65  call    __scrt_release_startup_lock
0x180007f6a  nop
0x180007f6b  add     rsp, 20h
0x180007f6f  pop     rbp
0x180007f70  retn
0x180007f72  push    rbp
0x180007f74  sub     rsp, 20h
0x180007f78  mov     rbp, rdx
0x180007f7b  add     rsp, 20h
0x180007f7f  pop     rbp
0x180007f80  jmp     __scrt_dllmain_uninitialize_critical
```
