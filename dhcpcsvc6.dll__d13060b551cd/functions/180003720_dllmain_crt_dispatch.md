# dllmain_crt_dispatch

- ea: `0x180003720`
- end: `0x180003770`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180003904`

## callees

- `0x180003720`
- `0x180003778`
- `0x180003878`
- `0x180003c48`
- `0x180003c78`

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
0x180003720  sub     rsp, 28h
0x180003724  test    edx, edx
0x180003726  jz      short loc_180003761
0x180003728  sub     edx, 1
0x18000372b  jz      short loc_180003755
0x18000372d  sub     edx, 1
0x180003730  jz      short loc_180003748
0x180003732  cmp     edx, 1
0x180003735  jz      short loc_180003741
0x180003737  mov     eax, 1
0x18000373c  add     rsp, 28h
0x180003740  retn
0x180003741  call    __scrt_dllmain_crt_thread_detach
0x180003746  jmp     short loc_18000374D
0x180003748  call    __scrt_dllmain_crt_thread_attach
0x18000374d  movzx   eax, al
0x180003750  add     rsp, 28h
0x180003754  retn
0x180003755  mov     rdx, r8
0x180003758  add     rsp, 28h
0x18000375c  jmp     dllmain_crt_process_attach
0x180003761  test    r8, r8
0x180003764  setnz   cl
0x180003767  add     rsp, 28h
0x18000376b  jmp     dllmain_crt_process_detach
```
