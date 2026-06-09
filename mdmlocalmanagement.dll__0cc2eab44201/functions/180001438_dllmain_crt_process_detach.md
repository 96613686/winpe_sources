# dllmain_crt_process_detach

- ea: `0x180001438`
- end: `0x1800014bb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800012e0`

## callees

- `0x180001438`
- `0x180001684`
- `0x1800017ac`
- `0x1800017e4`
- `0x180001974`
- `0x1800019a0`
- `0x180001b50`
- `0x180001b98`
- `0x180001be8`

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

  if ( dword_18000B290 <= 0 )
    return 0;
  --dword_18000B290;
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
0x180001438  mov     [rsp+arg_0], rbx
0x18000143d  push    rdi
0x18000143e  sub     rsp, 30h
0x180001442  mov     dil, cl
0x180001445  mov     eax, cs:dword_18000B290
0x18000144b  test    eax, eax
0x18000144d  jg      short loc_18000145C
0x18000144f  xor     eax, eax
0x180001451  mov     rbx, [rsp+38h+arg_0]
0x180001456  add     rsp, 30h
0x18000145a  pop     rdi
0x18000145b  retn
0x18000145c  dec     eax
0x18000145e  mov     cs:dword_18000B290, eax
0x180001464  call    __scrt_acquire_startup_lock
0x180001469  mov     bl, al
0x18000146b  mov     [rsp+38h+var_18], al
0x18000146f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001476  jnz     short loc_1800014AE
0x180001478  call    __scrt_dllmain_uninitialize_c
0x18000147d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001482  call    _RTC_Terminate
0x180001487  mov     cs:__scrt_current_native_startup_state, 0
0x180001491  mov     cl, bl
0x180001493  call    __scrt_release_startup_lock
0x180001498  xor     edx, edx
0x18000149a  mov     cl, dil
0x18000149d  call    __scrt_uninitialize_crt
0x1800014a2  movzx   ebx, al
0x1800014a5  call    __scrt_dllmain_uninitialize_critical
0x1800014aa  mov     eax, ebx
0x1800014ac  jmp     short loc_180001451
0x1800014ae  mov     ecx, 7
0x1800014b3  call    __scrt_fastfail
0x180006b99  push    rbp
0x180006b9b  sub     rsp, 20h
0x180006b9f  mov     rbp, rdx
0x180006ba2  mov     cl, [rbp+20h]
0x180006ba5  call    __scrt_release_startup_lock
0x180006baa  nop
0x180006bab  add     rsp, 20h
0x180006baf  pop     rbp
0x180006bb0  retn
0x180006bb2  push    rbp
0x180006bb4  sub     rsp, 20h
0x180006bb8  mov     rbp, rdx
0x180006bbb  add     rsp, 20h
0x180006bbf  pop     rbp
0x180006bc0  jmp     __scrt_dllmain_uninitialize_critical
```
