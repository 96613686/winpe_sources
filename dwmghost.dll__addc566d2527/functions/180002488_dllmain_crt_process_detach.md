# dllmain_crt_process_detach

- ea: `0x180002488`
- end: `0x18000250b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180002330`

## callees

- `0x1800011b4`
- `0x1800012dc`
- `0x180001314`
- `0x1800014a4`
- `0x1800014d0`
- `0x1800018b4`
- `0x180002488`
- `0x180002758`
- `0x1800027e4`

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

  if ( dword_180012240 <= 0 )
    return 0;
  --dword_180012240;
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
0x180002488  mov     [rsp+arg_0], rbx
0x18000248d  push    rdi
0x18000248e  sub     rsp, 30h
0x180002492  mov     dil, cl
0x180002495  mov     eax, cs:dword_180012240
0x18000249b  test    eax, eax
0x18000249d  jg      short loc_1800024AC
0x18000249f  xor     eax, eax
0x1800024a1  mov     rbx, [rsp+38h+arg_0]
0x1800024a6  add     rsp, 30h
0x1800024aa  pop     rdi
0x1800024ab  retn
0x1800024ac  dec     eax
0x1800024ae  mov     cs:dword_180012240, eax
0x1800024b4  call    __scrt_acquire_startup_lock
0x1800024b9  mov     bl, al
0x1800024bb  mov     [rsp+38h+var_18], al
0x1800024bf  cmp     cs:__scrt_current_native_startup_state, 2
0x1800024c6  jnz     short loc_1800024FE
0x1800024c8  call    __scrt_dllmain_uninitialize_c
0x1800024cd  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800024d2  call    _RTC_Terminate
0x1800024d7  mov     cs:__scrt_current_native_startup_state, 0
0x1800024e1  mov     cl, bl
0x1800024e3  call    __scrt_release_startup_lock
0x1800024e8  xor     edx, edx
0x1800024ea  mov     cl, dil
0x1800024ed  call    __scrt_uninitialize_crt
0x1800024f2  movzx   ebx, al
0x1800024f5  call    __scrt_dllmain_uninitialize_critical
0x1800024fa  mov     eax, ebx
0x1800024fc  jmp     short loc_1800024A1
0x1800024fe  mov     ecx, 7
0x180002503  call    __scrt_fastfail
0x18000b487  push    rbp
0x18000b489  sub     rsp, 20h
0x18000b48d  mov     rbp, rdx
0x18000b490  mov     cl, [rbp+20h]
0x18000b493  call    __scrt_release_startup_lock
0x18000b498  nop
0x18000b499  add     rsp, 20h
0x18000b49d  pop     rbp
0x18000b49e  retn
0x18000b4a0  push    rbp
0x18000b4a2  sub     rsp, 20h
0x18000b4a6  mov     rbp, rdx
0x18000b4a9  add     rsp, 20h
0x18000b4ad  pop     rbp
0x18000b4ae  jmp     __scrt_dllmain_uninitialize_critical
```
