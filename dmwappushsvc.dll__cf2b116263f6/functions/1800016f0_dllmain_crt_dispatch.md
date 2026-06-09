# dllmain_crt_dispatch

- ea: `0x1800016f0`
- end: `0x180001740`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800018d4`

## callees

- `0x1800016f0`
- `0x180001748`
- `0x180001848`
- `0x180001d24`
- `0x180001d54`

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
0x1800016f0  sub     rsp, 28h
0x1800016f4  test    edx, edx
0x1800016f6  jz      short loc_180001731
0x1800016f8  sub     edx, 1
0x1800016fb  jz      short loc_180001725
0x1800016fd  sub     edx, 1
0x180001700  jz      short loc_180001718
0x180001702  cmp     edx, 1
0x180001705  jz      short loc_180001711
0x180001707  mov     eax, 1
0x18000170c  add     rsp, 28h
0x180001710  retn
0x180001711  call    __scrt_dllmain_crt_thread_detach
0x180001716  jmp     short loc_18000171D
0x180001718  call    __scrt_dllmain_crt_thread_attach
0x18000171d  movzx   eax, al
0x180001720  add     rsp, 28h
0x180001724  retn
0x180001725  mov     rdx, r8
0x180001728  add     rsp, 28h
0x18000172c  jmp     dllmain_crt_process_attach
0x180001731  test    r8, r8
0x180001734  setnz   cl
0x180001737  add     rsp, 28h
0x18000173b  jmp     dllmain_crt_process_detach
```
