# dllmain_crt_process_detach

- ea: `0x180001ad8`
- end: `0x180001b5b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001980`

## callees

- `0x180001ad8`
- `0x180001d30`
- `0x180001e58`
- `0x180001e90`
- `0x180002020`
- `0x18000204c`
- `0x180002220`
- `0x180002268`
- `0x1800022b8`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // ebx

  if ( dword_180018350 <= 0 )
    return 0;
  --dword_180018350;
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
0x180001ad8  mov     [rsp+arg_0], rbx
0x180001add  push    rdi
0x180001ade  sub     rsp, 30h
0x180001ae2  mov     dil, cl
0x180001ae5  mov     eax, cs:dword_180018350
0x180001aeb  test    eax, eax
0x180001aed  jg      short loc_180001AFC
0x180001aef  xor     eax, eax
0x180001af1  mov     rbx, [rsp+38h+arg_0]
0x180001af6  add     rsp, 30h
0x180001afa  pop     rdi
0x180001afb  retn
0x180001afc  dec     eax
0x180001afe  mov     cs:dword_180018350, eax
0x180001b04  call    __scrt_acquire_startup_lock
0x180001b09  mov     bl, al
0x180001b0b  mov     [rsp+38h+var_18], al
0x180001b0f  cmp     cs:__scrt_current_native_startup_state, 2
0x180001b16  jnz     short loc_180001B4E
0x180001b18  call    __scrt_dllmain_uninitialize_c
0x180001b1d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001b22  call    _RTC_Terminate
0x180001b27  mov     cs:__scrt_current_native_startup_state, 0
0x180001b31  mov     cl, bl
0x180001b33  call    __scrt_release_startup_lock
0x180001b38  xor     edx, edx
0x180001b3a  mov     cl, dil
0x180001b3d  call    __scrt_uninitialize_crt
0x180001b42  movzx   ebx, al
0x180001b45  call    __scrt_dllmain_uninitialize_critical
0x180001b4a  mov     eax, ebx
0x180001b4c  jmp     short loc_180001AF1
0x180001b4e  mov     ecx, 7
0x180001b53  call    __scrt_fastfail
0x18000c7c9  push    rbp
0x18000c7cb  sub     rsp, 20h
0x18000c7cf  mov     rbp, rdx
0x18000c7d2  mov     cl, [rbp+20h]
0x18000c7d5  call    __scrt_release_startup_lock
0x18000c7da  nop
0x18000c7db  add     rsp, 20h
0x18000c7df  pop     rbp
0x18000c7e0  retn
0x18000c7e2  push    rbp
0x18000c7e4  sub     rsp, 20h
0x18000c7e8  mov     rbp, rdx
0x18000c7eb  add     rsp, 20h
0x18000c7ef  pop     rbp
0x18000c7f0  jmp     __scrt_dllmain_uninitialize_critical
```
