# dllmain_crt_process_detach

- ea: `0x1800011f8`
- end: `0x18000127b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800010a0`

## callees

- `0x1800011f8`
- `0x18000155c`
- `0x180001594`
- `0x1800016bc`
- `0x1800016f4`
- `0x180001884`
- `0x1800018b0`
- `0x1800018f0`
- `0x180001940`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_1800274D0 <= 0 )
    return 0;
  --dword_1800274D0;
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
0x1800011f8  mov     [rsp+arg_0], rbx
0x1800011fd  push    rdi
0x1800011fe  sub     rsp, 30h
0x180001202  mov     dil, cl
0x180001205  mov     eax, cs:dword_1800274D0
0x18000120b  test    eax, eax
0x18000120d  jg      short loc_18000121C
0x18000120f  xor     eax, eax
0x180001211  mov     rbx, [rsp+38h+arg_0]
0x180001216  add     rsp, 30h
0x18000121a  pop     rdi
0x18000121b  retn
0x18000121c  dec     eax
0x18000121e  mov     cs:dword_1800274D0, eax
0x180001224  call    __scrt_acquire_startup_lock
0x180001229  mov     bl, al
0x18000122b  mov     [rsp+38h+var_18], al
0x18000122f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001236  jnz     short loc_18000126E
0x180001238  call    __scrt_dllmain_uninitialize_c
0x18000123d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001242  call    _RTC_Terminate
0x180001247  mov     cs:__scrt_current_native_startup_state, 0
0x180001251  mov     cl, bl
0x180001253  call    __scrt_release_startup_lock
0x180001258  xor     edx, edx
0x18000125a  mov     cl, dil
0x18000125d  call    __scrt_uninitialize_crt
0x180001262  movzx   ebx, al
0x180001265  call    __scrt_dllmain_uninitialize_critical
0x18000126a  mov     eax, ebx
0x18000126c  jmp     short loc_180001211
0x18000126e  mov     ecx, 7
0x180001273  call    __scrt_fastfail
0x18001d429  push    rbp
0x18001d42b  sub     rsp, 20h
0x18001d42f  mov     rbp, rdx
0x18001d432  mov     cl, [rbp+20h]
0x18001d435  call    __scrt_release_startup_lock
0x18001d43a  nop
0x18001d43b  add     rsp, 20h
0x18001d43f  pop     rbp
0x18001d440  retn
0x18001d442  push    rbp
0x18001d444  sub     rsp, 20h
0x18001d448  mov     rbp, rdx
0x18001d44b  add     rsp, 20h
0x18001d44f  pop     rbp
0x18001d450  jmp     __scrt_dllmain_uninitialize_critical
```
