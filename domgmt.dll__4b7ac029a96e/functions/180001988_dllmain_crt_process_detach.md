# dllmain_crt_process_detach

- ea: `0x180001988`
- end: `0x180001a0b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001830`

## callees

- `0x180001988`
- `0x180001bc4`
- `0x180001cec`
- `0x180001d24`
- `0x180001eb4`
- `0x180001ee0`
- `0x180002450`
- `0x180002498`
- `0x1800024e8`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_180018590 <= 0 )
    return 0;
  --dword_180018590;
  v3 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
    _scrt_fastfail(7u);
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
0x180001988  mov     [rsp+arg_0], rbx
0x18000198d  push    rdi
0x18000198e  sub     rsp, 30h
0x180001992  mov     dil, cl
0x180001995  mov     eax, cs:dword_180018590
0x18000199b  test    eax, eax
0x18000199d  jg      short loc_1800019AC
0x18000199f  xor     eax, eax
0x1800019a1  mov     rbx, [rsp+38h+arg_0]
0x1800019a6  add     rsp, 30h
0x1800019aa  pop     rdi
0x1800019ab  retn
0x1800019ac  dec     eax
0x1800019ae  mov     cs:dword_180018590, eax
0x1800019b4  call    __scrt_acquire_startup_lock
0x1800019b9  mov     bl, al
0x1800019bb  mov     [rsp+38h+var_18], al
0x1800019bf  cmp     cs:__scrt_current_native_startup_state, 2
0x1800019c6  jnz     short loc_1800019FE
0x1800019c8  call    __scrt_dllmain_uninitialize_c
0x1800019cd  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800019d2  call    _RTC_Terminate
0x1800019d7  mov     cs:__scrt_current_native_startup_state, 0
0x1800019e1  mov     cl, bl
0x1800019e3  call    __scrt_release_startup_lock
0x1800019e8  xor     edx, edx
0x1800019ea  mov     cl, dil
0x1800019ed  call    __scrt_uninitialize_crt
0x1800019f2  movzx   ebx, al
0x1800019f5  call    __scrt_dllmain_uninitialize_critical
0x1800019fa  mov     eax, ebx
0x1800019fc  jmp     short loc_1800019A1
0x1800019fe  mov     ecx, 7
0x180001a03  call    __scrt_fastfail
0x18000d659  push    rbp
0x18000d65b  sub     rsp, 20h
0x18000d65f  mov     rbp, rdx
0x18000d662  mov     cl, [rbp+20h]
0x18000d665  call    __scrt_release_startup_lock
0x18000d66a  nop
0x18000d66b  add     rsp, 20h
0x18000d66f  pop     rbp
0x18000d670  retn
0x18000d672  push    rbp
0x18000d674  sub     rsp, 20h
0x18000d678  mov     rbp, rdx
0x18000d67b  add     rsp, 20h
0x18000d67f  pop     rbp
0x18000d680  jmp     __scrt_dllmain_uninitialize_critical
```
