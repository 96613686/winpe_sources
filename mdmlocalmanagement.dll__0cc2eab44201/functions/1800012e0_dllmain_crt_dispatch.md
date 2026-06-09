# dllmain_crt_dispatch

- ea: `0x1800012e0`
- end: `0x180001330`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800014c4`

## callees

- `0x1800012e0`
- `0x180001338`
- `0x180001438`
- `0x180001710`
- `0x180001740`

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
0x1800012e0  sub     rsp, 28h
0x1800012e4  test    edx, edx
0x1800012e6  jz      short loc_180001321
0x1800012e8  sub     edx, 1
0x1800012eb  jz      short loc_180001315
0x1800012ed  sub     edx, 1
0x1800012f0  jz      short loc_180001308
0x1800012f2  cmp     edx, 1
0x1800012f5  jz      short loc_180001301
0x1800012f7  mov     eax, 1
0x1800012fc  add     rsp, 28h
0x180001300  retn
0x180001301  call    __scrt_dllmain_crt_thread_detach
0x180001306  jmp     short loc_18000130D
0x180001308  call    __scrt_dllmain_crt_thread_attach
0x18000130d  movzx   eax, al
0x180001310  add     rsp, 28h
0x180001314  retn
0x180001315  mov     rdx, r8
0x180001318  add     rsp, 28h
0x18000131c  jmp     dllmain_crt_process_attach
0x180001321  test    r8, r8
0x180001324  setnz   cl
0x180001327  add     rsp, 28h
0x18000132b  jmp     dllmain_crt_process_detach
```
