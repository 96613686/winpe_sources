# dllmain_crt_dispatch

- ea: `0x180019760`
- end: `0x1800197b0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180019944`

## callees

- `0x180019760`
- `0x1800197b8`
- `0x1800198b8`
- `0x180019cb4`
- `0x180019ce4`

## pseudocode

```c
__int64 __fastcall dllmain_crt_dispatch(__int64 a1, int a2, __int64 a3)
{
  int v3; // edx
  int v4; // edx
  __int64 result; // rax

  if ( !a2 )
    return dllmain_crt_process_detach(a3 != 0);
  v3 = a2 - 1;
  if ( !v3 )
    return dllmain_crt_process_attach(a1, a3);
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

```

## disassembly

```asm
0x180019760  sub     rsp, 28h
0x180019764  test    edx, edx
0x180019766  jz      short loc_1800197A1
0x180019768  sub     edx, 1
0x18001976b  jz      short loc_180019795
0x18001976d  sub     edx, 1
0x180019770  jz      short loc_180019788
0x180019772  cmp     edx, 1
0x180019775  jz      short loc_180019781
0x180019777  mov     eax, 1
0x18001977c  add     rsp, 28h
0x180019780  retn
0x180019781  call    __scrt_dllmain_crt_thread_detach
0x180019786  jmp     short loc_18001978D
0x180019788  call    __scrt_dllmain_crt_thread_attach
0x18001978d  movzx   eax, al
0x180019790  add     rsp, 28h
0x180019794  retn
0x180019795  mov     rdx, r8
0x180019798  add     rsp, 28h
0x18001979c  jmp     dllmain_crt_process_attach
0x1800197a1  test    r8, r8
0x1800197a4  setnz   cl
0x1800197a7  add     rsp, 28h
0x1800197ab  jmp     dllmain_crt_process_detach
```
