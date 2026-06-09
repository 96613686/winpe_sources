# dllmain_crt_dispatch

- ea: `0x1800073d0`
- end: `0x180007420`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800075b4`

## callees

- `0x1800073d0`
- `0x180007428`
- `0x180007528`
- `0x1800078f8`
- `0x180007928`

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
0x1800073d0  sub     rsp, 28h
0x1800073d4  test    edx, edx
0x1800073d6  jz      short loc_180007411
0x1800073d8  sub     edx, 1
0x1800073db  jz      short loc_180007405
0x1800073dd  sub     edx, 1
0x1800073e0  jz      short loc_1800073F8
0x1800073e2  cmp     edx, 1
0x1800073e5  jz      short loc_1800073F1
0x1800073e7  mov     eax, 1
0x1800073ec  add     rsp, 28h
0x1800073f0  retn
0x1800073f1  call    __scrt_dllmain_crt_thread_detach
0x1800073f6  jmp     short loc_1800073FD
0x1800073f8  call    __scrt_dllmain_crt_thread_attach
0x1800073fd  movzx   eax, al
0x180007400  add     rsp, 28h
0x180007404  retn
0x180007405  mov     rdx, r8
0x180007408  add     rsp, 28h
0x18000740c  jmp     dllmain_crt_process_attach
0x180007411  test    r8, r8
0x180007414  setnz   cl
0x180007417  add     rsp, 28h
0x18000741b  jmp     dllmain_crt_process_detach
```
