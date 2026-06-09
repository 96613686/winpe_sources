# dllmain_crt_dispatch

- ea: `0x18000df80`
- end: `0x18000dfd0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000e164`

## callees

- `0x18000df80`
- `0x18000dfd8`
- `0x18000e0d8`
- `0x18000e4a8`
- `0x18000e4d8`

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
0x18000df80  sub     rsp, 28h
0x18000df84  test    edx, edx
0x18000df86  jz      short loc_18000DFC1
0x18000df88  sub     edx, 1
0x18000df8b  jz      short loc_18000DFB5
0x18000df8d  sub     edx, 1
0x18000df90  jz      short loc_18000DFA8
0x18000df92  cmp     edx, 1
0x18000df95  jz      short loc_18000DFA1
0x18000df97  mov     eax, 1
0x18000df9c  add     rsp, 28h
0x18000dfa0  retn
0x18000dfa1  call    __scrt_dllmain_crt_thread_detach
0x18000dfa6  jmp     short loc_18000DFAD
0x18000dfa8  call    __scrt_dllmain_crt_thread_attach
0x18000dfad  movzx   eax, al
0x18000dfb0  add     rsp, 28h
0x18000dfb4  retn
0x18000dfb5  mov     rdx, r8
0x18000dfb8  add     rsp, 28h
0x18000dfbc  jmp     dllmain_crt_process_attach
0x18000dfc1  test    r8, r8
0x18000dfc4  setnz   cl
0x18000dfc7  add     rsp, 28h
0x18000dfcb  jmp     dllmain_crt_process_detach
```
