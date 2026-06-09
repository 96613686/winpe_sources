# dllmain_crt_process_detach

- ea: `0x1800024a0`
- end: `0x180002520`
- name: `dllmain_crt_process_detach`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180002330`

## callees

- `0x1800024a0`
- `0x18000273c`
- `0x180002888`
- `0x1800028c0`
- `0x180002a50`
- `0x180002a7c`
- `0x180002c24`
- `0x180002c7c`
- `0x180002e28`

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

  if ( dword_180030490 <= 0 )
    return 0;
  --dword_180030490;
  v4 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
  {
    _scrt_fastfail(7);
    __debugbreak();
    JUMPOUT(0x180002520LL);
  }
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
0x1800024a0  mov     [rsp+arg_0], rbx
0x1800024a5  push    rdi
0x1800024a6  sub     rsp, 30h
0x1800024aa  mov     dil, cl
0x1800024ad  mov     eax, cs:dword_180030490
0x1800024b3  test    eax, eax
0x1800024b5  jg      short loc_1800024C4
0x1800024b7  xor     eax, eax
0x1800024b9  mov     rbx, [rsp+38h+arg_0]
0x1800024be  add     rsp, 30h
0x1800024c2  pop     rdi
0x1800024c3  retn
0x1800024c4  dec     eax
0x1800024c6  mov     cs:dword_180030490, eax
0x1800024cc  call    __scrt_acquire_startup_lock
0x1800024d1  mov     bl, al
0x1800024d3  mov     [rsp+38h+var_18], al
0x1800024d7  cmp     cs:__scrt_current_native_startup_state, 2
0x1800024de  jnz     short loc_180002513
0x1800024e0  call    __scrt_dllmain_uninitialize_c
0x1800024e5  call    ?__scrt_uninitialize_type_info@@YAXXZ
0x1800024ea  call    _RTC_Terminate
0x1800024ef  and     cs:__scrt_current_native_startup_state, 0
0x1800024f6  mov     cl, bl
0x1800024f8  call    __scrt_release_startup_lock
0x1800024fd  xor     edx, edx
0x1800024ff  mov     cl, dil
0x180002502  call    __scrt_uninitialize_crt
0x180002507  movzx   ebx, al
0x18000250a  call    __scrt_dllmain_uninitialize_critical
0x18000250f  mov     eax, ebx
0x180002511  jmp     short loc_1800024B9
0x180002513  mov     ecx, 7
0x180002518  call    __scrt_fastfail
0x18000251d  nop
0x18000251e  nop
0x18000251f  int     3; Trap to Debugger
0x180022099  push    rbp
0x18002209b  sub     rsp, 20h
0x18002209f  mov     rbp, rdx
0x1800220a2  mov     cl, [rbp+20h]
0x1800220a5  call    __scrt_release_startup_lock
0x1800220aa  nop
0x1800220ab  add     rsp, 20h
0x1800220af  pop     rbp
0x1800220b0  retn
0x1800220b2  push    rbp
0x1800220b4  sub     rsp, 20h
0x1800220b8  mov     rbp, rdx
0x1800220bb  add     rsp, 20h
0x1800220bf  pop     rbp
0x1800220c0  jmp     __scrt_dllmain_uninitialize_critical
```
