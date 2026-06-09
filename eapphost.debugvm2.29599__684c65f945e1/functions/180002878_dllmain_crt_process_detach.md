# dllmain_crt_process_detach

- ea: `0x180002878`
- end: `0x1800028fb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180002720`

## callees

- `0x180002878`
- `0x180002aec`
- `0x180002c14`
- `0x180002c4c`
- `0x180002ddc`
- `0x180002e08`
- `0x180002ed4`
- `0x180002fd8`
- `0x180003028`

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

  if ( dword_18004E090 <= 0 )
    return 0;
  --dword_18004E090;
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
0x180002878  mov     [rsp+arg_0], rbx
0x18000287d  push    rdi
0x18000287e  sub     rsp, 30h
0x180002882  mov     dil, cl
0x180002885  mov     eax, cs:dword_18004E090
0x18000288b  test    eax, eax
0x18000288d  jg      short loc_18000289C
0x18000288f  xor     eax, eax
0x180002891  mov     rbx, [rsp+38h+arg_0]
0x180002896  add     rsp, 30h
0x18000289a  pop     rdi
0x18000289b  retn
0x18000289c  dec     eax
0x18000289e  mov     cs:dword_18004E090, eax
0x1800028a4  call    __scrt_acquire_startup_lock
0x1800028a9  mov     bl, al
0x1800028ab  mov     [rsp+38h+var_18], al
0x1800028af  cmp     cs:__scrt_current_native_startup_state, 2
0x1800028b6  jnz     short loc_1800028EE
0x1800028b8  call    __scrt_dllmain_uninitialize_c
0x1800028bd  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800028c2  call    _RTC_Terminate
0x1800028c7  mov     cs:__scrt_current_native_startup_state, 0
0x1800028d1  mov     cl, bl
0x1800028d3  call    __scrt_release_startup_lock
0x1800028d8  xor     edx, edx
0x1800028da  mov     cl, dil
0x1800028dd  call    __scrt_uninitialize_crt
0x1800028e2  movzx   ebx, al
0x1800028e5  call    __scrt_dllmain_uninitialize_critical
0x1800028ea  mov     eax, ebx
0x1800028ec  jmp     short loc_180002891
0x1800028ee  mov     ecx, 7
0x1800028f3  call    __scrt_fastfail
0x180033e19  push    rbp
0x180033e1b  sub     rsp, 20h
0x180033e1f  mov     rbp, rdx
0x180033e22  mov     cl, [rbp+20h]
0x180033e25  call    __scrt_release_startup_lock
0x180033e2a  nop
0x180033e2b  add     rsp, 20h
0x180033e2f  pop     rbp
0x180033e30  retn
0x180033e32  push    rbp
0x180033e34  sub     rsp, 20h
0x180033e38  mov     rbp, rdx
0x180033e3b  add     rsp, 20h
0x180033e3f  pop     rbp
0x180033e40  jmp     __scrt_dllmain_uninitialize_critical
```
