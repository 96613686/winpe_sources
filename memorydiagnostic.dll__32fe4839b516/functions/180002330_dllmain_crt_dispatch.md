# dllmain_crt_dispatch

- ea: `0x180002330`
- end: `0x180002380`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180002528`

## callees

- `0x180002330`
- `0x180002388`
- `0x1800024a0`
- `0x1800027d4`
- `0x180002804`

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
0x180002330  sub     rsp, 28h
0x180002334  test    edx, edx
0x180002336  jz      short loc_180002371
0x180002338  sub     edx, 1
0x18000233b  jz      short loc_180002365
0x18000233d  sub     edx, 1
0x180002340  jz      short loc_180002358
0x180002342  cmp     edx, 1
0x180002345  jz      short loc_180002351
0x180002347  mov     eax, 1
0x18000234c  add     rsp, 28h
0x180002350  retn
0x180002351  call    __scrt_dllmain_crt_thread_detach
0x180002356  jmp     short loc_18000235D
0x180002358  call    __scrt_dllmain_crt_thread_attach
0x18000235d  movzx   eax, al
0x180002360  add     rsp, 28h
0x180002364  retn
0x180002365  mov     rdx, r8
0x180002368  add     rsp, 28h
0x18000236c  jmp     dllmain_crt_process_attach
0x180002371  test    r8, r8
0x180002374  setnz   cl
0x180002377  add     rsp, 28h
0x18000237b  jmp     dllmain_crt_process_detach
```
