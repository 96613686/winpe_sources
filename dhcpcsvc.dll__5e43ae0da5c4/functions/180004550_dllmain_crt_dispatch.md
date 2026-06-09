# dllmain_crt_dispatch

- ea: `0x180004550`
- end: `0x1800045a0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180004734`

## callees

- `0x180004550`
- `0x1800045a8`
- `0x1800046a8`
- `0x180004a78`
- `0x180004aa8`

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
0x180004550  sub     rsp, 28h
0x180004554  test    edx, edx
0x180004556  jz      short loc_180004591
0x180004558  sub     edx, 1
0x18000455b  jz      short loc_180004585
0x18000455d  sub     edx, 1
0x180004560  jz      short loc_180004578
0x180004562  cmp     edx, 1
0x180004565  jz      short loc_180004571
0x180004567  mov     eax, 1
0x18000456c  add     rsp, 28h
0x180004570  retn
0x180004571  call    __scrt_dllmain_crt_thread_detach
0x180004576  jmp     short loc_18000457D
0x180004578  call    __scrt_dllmain_crt_thread_attach
0x18000457d  movzx   eax, al
0x180004580  add     rsp, 28h
0x180004584  retn
0x180004585  mov     rdx, r8
0x180004588  add     rsp, 28h
0x18000458c  jmp     dllmain_crt_process_attach
0x180004591  test    r8, r8
0x180004594  setnz   cl
0x180004597  add     rsp, 28h
0x18000459b  jmp     dllmain_crt_process_detach
```
