# dllmain_crt_process_detach

- ea: `0x18000e0d8`
- end: `0x18000e15b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18000df80`

## callees

- `0x18000e0d8`
- `0x18000e3e4`
- `0x18000e41c`
- `0x18000e544`
- `0x18000e57c`
- `0x18000e70c`
- `0x18000e738`
- `0x18000e7d8`
- `0x18000e828`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_180020170 <= 0 )
    return 0;
  --dword_180020170;
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
0x18000e0d8  mov     [rsp+arg_0], rbx
0x18000e0dd  push    rdi
0x18000e0de  sub     rsp, 30h
0x18000e0e2  mov     dil, cl
0x18000e0e5  mov     eax, cs:dword_180020170
0x18000e0eb  test    eax, eax
0x18000e0ed  jg      short loc_18000E0FC
0x18000e0ef  xor     eax, eax
0x18000e0f1  mov     rbx, [rsp+38h+arg_0]
0x18000e0f6  add     rsp, 30h
0x18000e0fa  pop     rdi
0x18000e0fb  retn
0x18000e0fc  dec     eax
0x18000e0fe  mov     cs:dword_180020170, eax
0x18000e104  call    __scrt_acquire_startup_lock
0x18000e109  mov     bl, al
0x18000e10b  mov     [rsp+38h+var_18], al
0x18000e10f  cmp     cs:__scrt_current_native_startup_state, 2
0x18000e116  jnz     short loc_18000E14E
0x18000e118  call    __scrt_dllmain_uninitialize_c
0x18000e11d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x18000e122  call    _RTC_Terminate
0x18000e127  mov     cs:__scrt_current_native_startup_state, 0
0x18000e131  mov     cl, bl
0x18000e133  call    __scrt_release_startup_lock
0x18000e138  xor     edx, edx
0x18000e13a  mov     cl, dil
0x18000e13d  call    __scrt_uninitialize_crt
0x18000e142  movzx   ebx, al
0x18000e145  call    __scrt_dllmain_uninitialize_critical
0x18000e14a  mov     eax, ebx
0x18000e14c  jmp     short loc_18000E0F1
0x18000e14e  mov     ecx, 7
0x18000e153  call    __scrt_fastfail
0x180017599  push    rbp
0x18001759b  sub     rsp, 20h
0x18001759f  mov     rbp, rdx
0x1800175a2  mov     cl, [rbp+20h]
0x1800175a5  call    __scrt_release_startup_lock
0x1800175aa  nop
0x1800175ab  add     rsp, 20h
0x1800175af  pop     rbp
0x1800175b0  retn
0x1800175b2  push    rbp
0x1800175b4  sub     rsp, 20h
0x1800175b8  mov     rbp, rdx
0x1800175bb  add     rsp, 20h
0x1800175bf  pop     rbp
0x1800175c0  jmp     __scrt_dllmain_uninitialize_critical
```
