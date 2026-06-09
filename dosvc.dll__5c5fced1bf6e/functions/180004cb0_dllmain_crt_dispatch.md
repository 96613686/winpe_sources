# dllmain_crt_dispatch

- ea: `0x180004cb0`
- end: `0x180004d00`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180004e94`

## callees

- `0x180004cb0`
- `0x180004d08`
- `0x180004e08`
- `0x1800050d0`
- `0x180005100`

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
0x180004cb0  sub     rsp, 28h
0x180004cb4  test    edx, edx
0x180004cb6  jz      short loc_180004CF1
0x180004cb8  sub     edx, 1
0x180004cbb  jz      short loc_180004CE5
0x180004cbd  sub     edx, 1
0x180004cc0  jz      short loc_180004CD8
0x180004cc2  cmp     edx, 1
0x180004cc5  jz      short loc_180004CD1
0x180004cc7  mov     eax, 1
0x180004ccc  add     rsp, 28h
0x180004cd0  retn
0x180004cd1  call    __scrt_dllmain_crt_thread_detach
0x180004cd6  jmp     short loc_180004CDD
0x180004cd8  call    __scrt_dllmain_crt_thread_attach
0x180004cdd  movzx   eax, al
0x180004ce0  add     rsp, 28h
0x180004ce4  retn
0x180004ce5  mov     rdx, r8
0x180004ce8  add     rsp, 28h
0x180004cec  jmp     dllmain_crt_process_attach
0x180004cf1  test    r8, r8
0x180004cf4  setnz   cl
0x180004cf7  add     rsp, 28h
0x180004cfb  jmp     dllmain_crt_process_detach
```
