# dllmain_crt_dispatch

- ea: `0x180014a50`
- end: `0x180014aa0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180014c34`

## callees

- `0x180014a50`
- `0x180014aa8`
- `0x180014ba8`
- `0x180014fa4`
- `0x180014fd4`

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
0x180014a50  sub     rsp, 28h
0x180014a54  test    edx, edx
0x180014a56  jz      short loc_180014A91
0x180014a58  sub     edx, 1
0x180014a5b  jz      short loc_180014A85
0x180014a5d  sub     edx, 1
0x180014a60  jz      short loc_180014A78
0x180014a62  cmp     edx, 1
0x180014a65  jz      short loc_180014A71
0x180014a67  mov     eax, 1
0x180014a6c  add     rsp, 28h
0x180014a70  retn
0x180014a71  call    __scrt_dllmain_crt_thread_detach
0x180014a76  jmp     short loc_180014A7D
0x180014a78  call    __scrt_dllmain_crt_thread_attach
0x180014a7d  movzx   eax, al
0x180014a80  add     rsp, 28h
0x180014a84  retn
0x180014a85  mov     rdx, r8
0x180014a88  add     rsp, 28h
0x180014a8c  jmp     dllmain_crt_process_attach
0x180014a91  test    r8, r8
0x180014a94  setnz   cl
0x180014a97  add     rsp, 28h
0x180014a9b  jmp     dllmain_crt_process_detach
```
