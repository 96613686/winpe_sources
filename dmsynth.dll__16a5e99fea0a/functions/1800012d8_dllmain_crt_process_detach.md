# dllmain_crt_process_detach

- ea: `0x1800012d8`
- end: `0x18000135b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001180`

## callees

- `0x1800012d8`
- `0x180001610`
- `0x180001648`
- `0x180001770`
- `0x1800017a8`
- `0x180001938`
- `0x180001964`
- `0x1800019a4`
- `0x1800019f4`

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

  if ( dword_18001E630 <= 0 )
    return 0;
  --dword_18001E630;
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
0x1800012d8  mov     [rsp+arg_0], rbx
0x1800012dd  push    rdi
0x1800012de  sub     rsp, 30h
0x1800012e2  mov     dil, cl
0x1800012e5  mov     eax, cs:dword_18001E630
0x1800012eb  test    eax, eax
0x1800012ed  jg      short loc_1800012FC
0x1800012ef  xor     eax, eax
0x1800012f1  mov     rbx, [rsp+38h+arg_0]
0x1800012f6  add     rsp, 30h
0x1800012fa  pop     rdi
0x1800012fb  retn
0x1800012fc  dec     eax
0x1800012fe  mov     cs:dword_18001E630, eax
0x180001304  call    __scrt_acquire_startup_lock
0x180001309  mov     bl, al
0x18000130b  mov     [rsp+38h+var_18], al
0x18000130f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001316  jnz     short loc_18000134E
0x180001318  call    __scrt_dllmain_uninitialize_c
0x18000131d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001322  call    _RTC_Terminate
0x180001327  mov     cs:__scrt_current_native_startup_state, 0
0x180001331  mov     cl, bl
0x180001333  call    __scrt_release_startup_lock
0x180001338  xor     edx, edx
0x18000133a  mov     cl, dil
0x18000133d  call    __scrt_uninitialize_crt
0x180001342  movzx   ebx, al
0x180001345  call    __scrt_dllmain_uninitialize_critical
0x18000134a  mov     eax, ebx
0x18000134c  jmp     short loc_1800012F1
0x18000134e  mov     ecx, 7
0x180001353  call    __scrt_fastfail
0x18001496d  push    rbp
0x18001496f  sub     rsp, 20h
0x180014973  mov     rbp, rdx
0x180014976  mov     cl, [rbp+20h]
0x180014979  call    __scrt_release_startup_lock
0x18001497e  nop
0x18001497f  add     rsp, 20h
0x180014983  pop     rbp
0x180014984  retn
0x180014986  push    rbp
0x180014988  sub     rsp, 20h
0x18001498c  mov     rbp, rdx
0x18001498f  add     rsp, 20h
0x180014993  pop     rbp
0x180014994  jmp     __scrt_dllmain_uninitialize_critical
```
