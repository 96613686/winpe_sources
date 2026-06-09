# dllmain_crt_process_detach

- ea: `0x180003878`
- end: `0x1800038fb`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: `__int64 __fastcall(char)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180003720`

## callees

- `0x180003878`
- `0x180003b84`
- `0x180003bbc`
- `0x180003ce4`
- `0x180003d1c`
- `0x180003eac`
- `0x180003ed8`
- `0x180003f18`
- `0x180003f68`

## pseudocode

```c
__int64 __fastcall dllmain_crt_process_detach(char a1)
{
  char v3; // bl
  __int64 v4; // rcx
  unsigned int v5; // ebx

  if ( dword_18000F090 <= 0 )
    return 0;
  --dword_18000F090;
  v3 = _scrt_acquire_startup_lock();
  if ( _scrt_current_native_startup_state != 2 )
    _scrt_fastfail(7u);
  _scrt_dllmain_uninitialize_c();
  __scrt_uninitialize_type_info();
  RTC_Terminate();
  _scrt_current_native_startup_state = 0;
  _scrt_release_startup_lock(v3);
  LOBYTE(v4) = a1;
  v5 = (unsigned __int8)_scrt_uninitialize_crt(v4, 0);
  _scrt_dllmain_uninitialize_critical();
  return v5;
}

```

## disassembly

```asm
0x180003878  mov     [rsp+arg_0], rbx
0x18000387d  push    rdi
0x18000387e  sub     rsp, 30h
0x180003882  mov     dil, cl
0x180003885  mov     eax, cs:dword_18000F090
0x18000388b  test    eax, eax
0x18000388d  jg      short loc_18000389C
0x18000388f  xor     eax, eax
0x180003891  mov     rbx, [rsp+38h+arg_0]
0x180003896  add     rsp, 30h
0x18000389a  pop     rdi
0x18000389b  retn
0x18000389c  dec     eax
0x18000389e  mov     cs:dword_18000F090, eax
0x1800038a4  call    __scrt_acquire_startup_lock
0x1800038a9  mov     bl, al
0x1800038ab  mov     [rsp+38h+var_18], al
0x1800038af  cmp     cs:__scrt_current_native_startup_state, 2
0x1800038b6  jnz     short loc_1800038EE
0x1800038b8  call    __scrt_dllmain_uninitialize_c
0x1800038bd  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x1800038c2  call    _RTC_Terminate
0x1800038c7  mov     cs:__scrt_current_native_startup_state, 0
0x1800038d1  mov     cl, bl
0x1800038d3  call    __scrt_release_startup_lock
0x1800038d8  xor     edx, edx
0x1800038da  mov     cl, dil
0x1800038dd  call    __scrt_uninitialize_crt
0x1800038e2  movzx   ebx, al
0x1800038e5  call    __scrt_dllmain_uninitialize_critical
0x1800038ea  mov     eax, ebx
0x1800038ec  jmp     short loc_180003891
0x1800038ee  mov     ecx, 7
0x1800038f3  call    __scrt_fastfail
0x18000797f  push    rbp
0x180007981  sub     rsp, 20h
0x180007985  mov     rbp, rdx
0x180007988  mov     cl, [rbp+20h]
0x18000798b  call    __scrt_release_startup_lock
0x180007990  nop
0x180007991  add     rsp, 20h
0x180007995  pop     rbp
0x180007996  retn
0x180007998  push    rbp
0x18000799a  sub     rsp, 20h
0x18000799e  mov     rbp, rdx
0x1800079a1  add     rsp, 20h
0x1800079a5  pop     rbp
0x1800079a6  jmp     __scrt_dllmain_uninitialize_critical
```
