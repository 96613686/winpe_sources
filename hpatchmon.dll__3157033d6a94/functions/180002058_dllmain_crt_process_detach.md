# dllmain_crt_process_detach

- ea: `0x180002058`
- end: `0x1800020db`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001f00`

## callees

- `0x180002058`
- `0x180002294`
- `0x1800023bc`
- `0x1800023f4`
- `0x180002584`
- `0x1800025b0`
- `0x180002710`
- `0x180002758`
- `0x1800027a8`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_18001E750 <= 0 )
    return 0;
  --dword_18001E750;
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
0x180002058  mov     [rsp+arg_0], rbx
0x18000205d  push    rdi
0x18000205e  sub     rsp, 30h
0x180002062  mov     dil, cl
0x180002065  mov     eax, cs:dword_18001E750
0x18000206b  test    eax, eax
0x18000206d  jg      short loc_18000207C
0x18000206f  xor     eax, eax
0x180002071  mov     rbx, [rsp+38h+arg_0]
0x180002076  add     rsp, 30h
0x18000207a  pop     rdi
0x18000207b  retn
0x18000207c  dec     eax
0x18000207e  mov     cs:dword_18001E750, eax
0x180002084  call    __scrt_acquire_startup_lock
0x180002089  mov     bl, al
0x18000208b  mov     [rsp+38h+var_18], al
0x18000208f  cmp     cs:__scrt_current_native_startup_state, 2
0x180002096  jnz     short loc_1800020CE
0x180002098  call    __scrt_dllmain_uninitialize_c
0x18000209d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800020a2  call    _RTC_Terminate
0x1800020a7  mov     cs:__scrt_current_native_startup_state, 0
0x1800020b1  mov     cl, bl
0x1800020b3  call    __scrt_release_startup_lock
0x1800020b8  xor     edx, edx
0x1800020ba  mov     cl, dil
0x1800020bd  call    __scrt_uninitialize_crt
0x1800020c2  movzx   ebx, al
0x1800020c5  call    __scrt_dllmain_uninitialize_critical
0x1800020ca  mov     eax, ebx
0x1800020cc  jmp     short loc_180002071
0x1800020ce  mov     ecx, 7
0x1800020d3  call    __scrt_fastfail
0x1800140f9  push    rbp
0x1800140fb  sub     rsp, 20h
0x1800140ff  mov     rbp, rdx
0x180014102  mov     cl, [rbp+20h]
0x180014105  call    __scrt_release_startup_lock
0x18001410a  nop
0x18001410b  add     rsp, 20h
0x18001410f  pop     rbp
0x180014110  retn
0x180014112  push    rbp
0x180014114  sub     rsp, 20h
0x180014118  mov     rbp, rdx
0x18001411b  add     rsp, 20h
0x18001411f  pop     rbp
0x180014120  jmp     __scrt_dllmain_uninitialize_critical
```
