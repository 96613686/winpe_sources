# dllmain_crt_process_detach

- ea: `0x1800028d8`
- end: `0x18000295b`
- name: `dllmain_crt_process_detach`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180002780`

## callees

- `0x1800028d8`
- `0x180002b4c`
- `0x180002c74`
- `0x180002cac`
- `0x180002e3c`
- `0x180002e68`
- `0x180002f34`
- `0x180003038`
- `0x180003088`

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

  if ( dword_18004F1D0 <= 0 )
    return 0;
  --dword_18004F1D0;
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
0x1800028d8  mov     [rsp+arg_0], rbx
0x1800028dd  push    rdi
0x1800028de  sub     rsp, 30h
0x1800028e2  mov     dil, cl
0x1800028e5  mov     eax, cs:dword_18004F1D0
0x1800028eb  test    eax, eax
0x1800028ed  jg      short loc_1800028FC
0x1800028ef  xor     eax, eax
0x1800028f1  mov     rbx, [rsp+38h+arg_0]
0x1800028f6  add     rsp, 30h
0x1800028fa  pop     rdi
0x1800028fb  retn
0x1800028fc  dec     eax
0x1800028fe  mov     cs:dword_18004F1D0, eax
0x180002904  call    __scrt_acquire_startup_lock
0x180002909  mov     bl, al
0x18000290b  mov     [rsp+38h+var_18], al
0x18000290f  cmp     cs:__scrt_current_native_startup_state, 2
0x180002916  jnz     short loc_18000294E
0x180002918  call    __scrt_dllmain_uninitialize_c
0x18000291d  call    ?__scrt_uninitialize_type_info@@YAXXZ; __scrt_uninitialize_type_info(void)
0x180002922  call    _RTC_Terminate
0x180002927  mov     cs:__scrt_current_native_startup_state, 0
0x180002931  mov     cl, bl
0x180002933  call    __scrt_release_startup_lock
0x180002938  xor     edx, edx
0x18000293a  mov     cl, dil
0x18000293d  call    __scrt_uninitialize_crt
0x180002942  movzx   ebx, al
0x180002945  call    __scrt_dllmain_uninitialize_critical
0x18000294a  mov     eax, ebx
0x18000294c  jmp     short loc_1800028F1
0x18000294e  mov     ecx, 7
0x180002953  call    __scrt_fastfail
0x1800351d9  push    rbp
0x1800351db  sub     rsp, 20h
0x1800351df  mov     rbp, rdx
0x1800351e2  mov     cl, [rbp+20h]
0x1800351e5  call    __scrt_release_startup_lock
0x1800351ea  nop
0x1800351eb  add     rsp, 20h
0x1800351ef  pop     rbp
0x1800351f0  retn
0x1800351f2  push    rbp
0x1800351f4  sub     rsp, 20h
0x1800351f8  mov     rbp, rdx
0x1800351fb  add     rsp, 20h
0x1800351ff  pop     rbp
0x180035200  jmp     __scrt_dllmain_uninitialize_critical
```
