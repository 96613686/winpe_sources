# dllmain_crt_process_detach

- ea: `0x180013908`
- end: `0x18001398b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800137b0`

## callees

- `0x180013908`
- `0x180013bdc`
- `0x180013d04`
- `0x180013d3c`
- `0x180013ecc`
- `0x180013ef8`
- `0x18001409c`
- `0x1800140e4`
- `0x180014134`

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

  if ( dword_1800335D0 <= 0 )
    return 0;
  --dword_1800335D0;
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
0x180013908  mov     [rsp+arg_0], rbx
0x18001390d  push    rdi
0x18001390e  sub     rsp, 30h
0x180013912  mov     dil, cl
0x180013915  mov     eax, cs:dword_1800335D0
0x18001391b  test    eax, eax
0x18001391d  jg      short loc_18001392C
0x18001391f  xor     eax, eax
0x180013921  mov     rbx, [rsp+38h+arg_0]
0x180013926  add     rsp, 30h
0x18001392a  pop     rdi
0x18001392b  retn
0x18001392c  dec     eax
0x18001392e  mov     cs:dword_1800335D0, eax
0x180013934  call    __scrt_acquire_startup_lock
0x180013939  mov     bl, al
0x18001393b  mov     [rsp+38h+var_18], al
0x18001393f  cmp     cs:__scrt_current_native_startup_state, 2
0x180013946  jnz     short loc_18001397E
0x180013948  call    __scrt_dllmain_uninitialize_c
0x18001394d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180013952  call    _RTC_Terminate
0x180013957  mov     cs:__scrt_current_native_startup_state, 0
0x180013961  mov     cl, bl
0x180013963  call    __scrt_release_startup_lock
0x180013968  xor     edx, edx
0x18001396a  mov     cl, dil
0x18001396d  call    __scrt_uninitialize_crt
0x180013972  movzx   ebx, al
0x180013975  call    __scrt_dllmain_uninitialize_critical
0x18001397a  mov     eax, ebx
0x18001397c  jmp     short loc_180013921
0x18001397e  mov     ecx, 7
0x180013983  call    __scrt_fastfail
0x18002618f  push    rbp
0x180026191  sub     rsp, 20h
0x180026195  mov     rbp, rdx
0x180026198  mov     cl, [rbp+20h]
0x18002619b  call    __scrt_release_startup_lock
0x1800261a0  nop
0x1800261a1  add     rsp, 20h
0x1800261a5  pop     rbp
0x1800261a6  retn
0x1800261a8  push    rbp
0x1800261aa  sub     rsp, 20h
0x1800261ae  mov     rbp, rdx
0x1800261b1  add     rsp, 20h
0x1800261b5  pop     rbp
0x1800261b6  jmp     __scrt_dllmain_uninitialize_critical
```
