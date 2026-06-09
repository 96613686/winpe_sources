# dllmain_crt_process_detach

- ea: `0x180001838`
- end: `0x1800018bb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800016e0`

## callees

- `0x180001838`
- `0x180001a80`
- `0x180001ba8`
- `0x180001be0`
- `0x180001d70`
- `0x180001d9c`
- `0x180001f78`
- `0x180001fc0`
- `0x180002010`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_180019610 <= 0 )
    return 0;
  --dword_180019610;
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
0x180001838  mov     [rsp+arg_0], rbx
0x18000183d  push    rdi
0x18000183e  sub     rsp, 30h
0x180001842  mov     dil, cl
0x180001845  mov     eax, cs:dword_180019610
0x18000184b  test    eax, eax
0x18000184d  jg      short loc_18000185C
0x18000184f  xor     eax, eax
0x180001851  mov     rbx, [rsp+38h+arg_0]
0x180001856  add     rsp, 30h
0x18000185a  pop     rdi
0x18000185b  retn
0x18000185c  dec     eax
0x18000185e  mov     cs:dword_180019610, eax
0x180001864  call    __scrt_acquire_startup_lock
0x180001869  mov     bl, al
0x18000186b  mov     [rsp+38h+var_18], al
0x18000186f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001876  jnz     short loc_1800018AE
0x180001878  call    __scrt_dllmain_uninitialize_c
0x18000187d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001882  call    _RTC_Terminate
0x180001887  mov     cs:__scrt_current_native_startup_state, 0
0x180001891  mov     cl, bl
0x180001893  call    __scrt_release_startup_lock
0x180001898  xor     edx, edx
0x18000189a  mov     cl, dil
0x18000189d  call    __scrt_uninitialize_crt
0x1800018a2  movzx   ebx, al
0x1800018a5  call    __scrt_dllmain_uninitialize_critical
0x1800018aa  mov     eax, ebx
0x1800018ac  jmp     short loc_180001851
0x1800018ae  mov     ecx, 7
0x1800018b3  call    __scrt_fastfail
0x180010819  push    rbp
0x18001081b  sub     rsp, 20h
0x18001081f  mov     rbp, rdx
0x180010822  mov     cl, [rbp+20h]
0x180010825  call    __scrt_release_startup_lock
0x18001082a  nop
0x18001082b  add     rsp, 20h
0x18001082f  pop     rbp
0x180010830  retn
0x180010832  push    rbp
0x180010834  sub     rsp, 20h
0x180010838  mov     rbp, rdx
0x18001083b  add     rsp, 20h
0x18001083f  pop     rbp
0x180010840  jmp     __scrt_dllmain_uninitialize_critical
```
