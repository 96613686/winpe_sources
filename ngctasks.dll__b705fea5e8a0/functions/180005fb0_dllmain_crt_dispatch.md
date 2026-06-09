# dllmain_crt_dispatch

- ea: `0x180005fb0`
- end: `0x180006000`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180006194`

## callees

- `0x180005fb0`
- `0x180006008`
- `0x180006108`
- `0x1800064d4`
- `0x180006504`

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
0x180005fb0  sub     rsp, 28h
0x180005fb4  test    edx, edx
0x180005fb6  jz      short loc_180005FF1
0x180005fb8  sub     edx, 1
0x180005fbb  jz      short loc_180005FE5
0x180005fbd  sub     edx, 1
0x180005fc0  jz      short loc_180005FD8
0x180005fc2  cmp     edx, 1
0x180005fc5  jz      short loc_180005FD1
0x180005fc7  mov     eax, 1
0x180005fcc  add     rsp, 28h
0x180005fd0  retn
0x180005fd1  call    __scrt_dllmain_crt_thread_detach
0x180005fd6  jmp     short loc_180005FDD
0x180005fd8  call    __scrt_dllmain_crt_thread_attach
0x180005fdd  movzx   eax, al
0x180005fe0  add     rsp, 28h
0x180005fe4  retn
0x180005fe5  mov     rdx, r8
0x180005fe8  add     rsp, 28h
0x180005fec  jmp     dllmain_crt_process_attach
0x180005ff1  test    r8, r8
0x180005ff4  setnz   cl
0x180005ff7  add     rsp, 28h
0x180005ffb  jmp     dllmain_crt_process_detach
```
