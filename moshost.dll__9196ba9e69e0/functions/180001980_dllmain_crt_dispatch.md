# dllmain_crt_dispatch

- ea: `0x180001980`
- end: `0x1800019d0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001b64`

## callees

- `0x180001980`
- `0x1800019d8`
- `0x180001ad8`
- `0x180001dbc`
- `0x180001dec`

## pseudocode

```c
__int64 __fastcall dllmain_crt_dispatch(__int64 a1, int a2, __int64 a3)
{
  int v3; // edx
  int v4; // edx
  __int64 result; // rax

  if ( a2 )
  {
    v3 = a2 - 1;
    if ( v3 )
    {
      v4 = v3 - 1;
      if ( v4 )
      {
        if ( v4 != 1 )
          return 1;
        LOBYTE(result) = _scrt_dllmain_crt_thread_detach();
      }
      else
      {
        LOBYTE(result) = _scrt_dllmain_crt_thread_attach();
      }
      return (unsigned __int8)result;
    }
    else
    {
      return dllmain_crt_process_attach(a1, a3);
    }
  }
  else
  {
    LOBYTE(a1) = a3 != 0;
    return dllmain_crt_process_detach(a1);
  }
}

```

## disassembly

```asm
0x180001980  sub     rsp, 28h
0x180001984  test    edx, edx
0x180001986  jz      short loc_1800019C1
0x180001988  sub     edx, 1
0x18000198b  jz      short loc_1800019B5
0x18000198d  sub     edx, 1
0x180001990  jz      short loc_1800019A8
0x180001992  cmp     edx, 1
0x180001995  jz      short loc_1800019A1
0x180001997  mov     eax, 1
0x18000199c  add     rsp, 28h
0x1800019a0  retn
0x1800019a1  call    __scrt_dllmain_crt_thread_detach
0x1800019a6  jmp     short loc_1800019AD
0x1800019a8  call    __scrt_dllmain_crt_thread_attach
0x1800019ad  movzx   eax, al
0x1800019b0  add     rsp, 28h
0x1800019b4  retn
0x1800019b5  mov     rdx, r8
0x1800019b8  add     rsp, 28h
0x1800019bc  jmp     dllmain_crt_process_attach
0x1800019c1  test    r8, r8
0x1800019c4  setnz   cl
0x1800019c7  add     rsp, 28h
0x1800019cb  jmp     dllmain_crt_process_detach
```
