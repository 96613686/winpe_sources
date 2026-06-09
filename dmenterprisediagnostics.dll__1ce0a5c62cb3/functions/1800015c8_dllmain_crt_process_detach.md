# dllmain_crt_process_detach

- ea: `0x1800015c8`
- end: `0x18000164b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180001470`

## callees

- `0x1800015c8`
- `0x180001930`
- `0x180001a58`
- `0x180001a90`
- `0x180001c20`
- `0x180001c4c`
- `0x180001dfc`
- `0x180001e44`
- `0x180001e94`

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

  if ( dword_180033D10 <= 0 )
    return 0;
  --dword_180033D10;
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
0x1800015c8  mov     [rsp+arg_0], rbx
0x1800015cd  push    rdi
0x1800015ce  sub     rsp, 30h
0x1800015d2  mov     dil, cl
0x1800015d5  mov     eax, cs:dword_180033D10
0x1800015db  test    eax, eax
0x1800015dd  jg      short loc_1800015EC
0x1800015df  xor     eax, eax
0x1800015e1  mov     rbx, [rsp+38h+arg_0]
0x1800015e6  add     rsp, 30h
0x1800015ea  pop     rdi
0x1800015eb  retn
0x1800015ec  dec     eax
0x1800015ee  mov     cs:dword_180033D10, eax
0x1800015f4  call    __scrt_acquire_startup_lock
0x1800015f9  mov     bl, al
0x1800015fb  mov     [rsp+38h+var_18], al
0x1800015ff  cmp     cs:__scrt_current_native_startup_state, 2
0x180001606  jnz     short loc_18000163E
0x180001608  call    __scrt_dllmain_uninitialize_c
0x18000160d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180001612  call    _RTC_Terminate
0x180001617  mov     cs:__scrt_current_native_startup_state, 0
0x180001621  mov     cl, bl
0x180001623  call    __scrt_release_startup_lock
0x180001628  xor     edx, edx
0x18000162a  mov     cl, dil
0x18000162d  call    __scrt_uninitialize_crt
0x180001632  movzx   ebx, al
0x180001635  call    __scrt_dllmain_uninitialize_critical
0x18000163a  mov     eax, ebx
0x18000163c  jmp     short loc_1800015E1
0x18000163e  mov     ecx, 7
0x180001643  call    __scrt_fastfail
0x180024479  push    rbp
0x18002447b  sub     rsp, 20h
0x18002447f  mov     rbp, rdx
0x180024482  mov     cl, [rbp+20h]
0x180024485  call    __scrt_release_startup_lock
0x18002448a  nop
0x18002448b  add     rsp, 20h
0x18002448f  pop     rbp
0x180024490  retn
0x180024492  push    rbp
0x180024494  sub     rsp, 20h
0x180024498  mov     rbp, rdx
0x18002449b  add     rsp, 20h
0x18002449f  pop     rbp
0x1800244a0  jmp     __scrt_dllmain_uninitialize_critical
```
