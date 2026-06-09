# dllmain_crt_dispatch

- ea: `0x1800012d0`
- end: `0x180001320`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800014b4`

## callees

- `0x1800012d0`
- `0x180001328`
- `0x180001428`
- `0x1800017f8`
- `0x180001828`

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
0x1800012d0  sub     rsp, 28h
0x1800012d4  test    edx, edx
0x1800012d6  jz      short loc_180001311
0x1800012d8  sub     edx, 1
0x1800012db  jz      short loc_180001305
0x1800012dd  sub     edx, 1
0x1800012e0  jz      short loc_1800012F8
0x1800012e2  cmp     edx, 1
0x1800012e5  jz      short loc_1800012F1
0x1800012e7  mov     eax, 1
0x1800012ec  add     rsp, 28h
0x1800012f0  retn
0x1800012f1  call    __scrt_dllmain_crt_thread_detach
0x1800012f6  jmp     short loc_1800012FD
0x1800012f8  call    __scrt_dllmain_crt_thread_attach
0x1800012fd  movzx   eax, al
0x180001300  add     rsp, 28h
0x180001304  retn
0x180001305  mov     rdx, r8
0x180001308  add     rsp, 28h
0x18000130c  jmp     dllmain_crt_process_attach
0x180001311  test    r8, r8
0x180001314  setnz   cl
0x180001317  add     rsp, 28h
0x18000131b  jmp     dllmain_crt_process_detach
```
