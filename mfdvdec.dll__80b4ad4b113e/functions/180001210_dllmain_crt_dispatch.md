# dllmain_crt_dispatch

- ea: `0x180001210`
- end: `0x180001260`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800013f4`

## callees

- `0x180001210`
- `0x180001268`
- `0x180001368`
- `0x180001738`
- `0x180001768`

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
0x180001210  sub     rsp, 28h
0x180001214  test    edx, edx
0x180001216  jz      short loc_180001251
0x180001218  sub     edx, 1
0x18000121b  jz      short loc_180001245
0x18000121d  sub     edx, 1
0x180001220  jz      short loc_180001238
0x180001222  cmp     edx, 1
0x180001225  jz      short loc_180001231
0x180001227  mov     eax, 1
0x18000122c  add     rsp, 28h
0x180001230  retn
0x180001231  call    __scrt_dllmain_crt_thread_detach
0x180001236  jmp     short loc_18000123D
0x180001238  call    __scrt_dllmain_crt_thread_attach
0x18000123d  movzx   eax, al
0x180001240  add     rsp, 28h
0x180001244  retn
0x180001245  mov     rdx, r8
0x180001248  add     rsp, 28h
0x18000124c  jmp     dllmain_crt_process_attach
0x180001251  test    r8, r8
0x180001254  setnz   cl
0x180001257  add     rsp, 28h
0x18000125b  jmp     dllmain_crt_process_detach
```
