# dllmain_crt_dispatch

- ea: `0x180015d20`
- end: `0x180015d70`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180015f04`

## callees

- `0x180015d20`
- `0x180015d78`
- `0x180015e78`
- `0x1800162e0`
- `0x180016310`

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
0x180015d20  sub     rsp, 28h
0x180015d24  test    edx, edx
0x180015d26  jz      short loc_180015D61
0x180015d28  sub     edx, 1
0x180015d2b  jz      short loc_180015D55
0x180015d2d  sub     edx, 1
0x180015d30  jz      short loc_180015D48
0x180015d32  cmp     edx, 1
0x180015d35  jz      short loc_180015D41
0x180015d37  mov     eax, 1
0x180015d3c  add     rsp, 28h
0x180015d40  retn
0x180015d41  call    __scrt_dllmain_crt_thread_detach
0x180015d46  jmp     short loc_180015D4D
0x180015d48  call    __scrt_dllmain_crt_thread_attach
0x180015d4d  movzx   eax, al
0x180015d50  add     rsp, 28h
0x180015d54  retn
0x180015d55  mov     rdx, r8
0x180015d58  add     rsp, 28h
0x180015d5c  jmp     dllmain_crt_process_attach
0x180015d61  test    r8, r8
0x180015d64  setnz   cl
0x180015d67  add     rsp, 28h
0x180015d6b  jmp     dllmain_crt_process_detach
```
