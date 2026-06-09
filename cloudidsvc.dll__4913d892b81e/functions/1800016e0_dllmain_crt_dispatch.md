# dllmain_crt_dispatch

- ea: `0x1800016e0`
- end: `0x180001730`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800018c4`

## callees

- `0x1800016e0`
- `0x180001738`
- `0x180001838`
- `0x180001b0c`
- `0x180001b3c`

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
0x1800016e0  sub     rsp, 28h
0x1800016e4  test    edx, edx
0x1800016e6  jz      short loc_180001721
0x1800016e8  sub     edx, 1
0x1800016eb  jz      short loc_180001715
0x1800016ed  sub     edx, 1
0x1800016f0  jz      short loc_180001708
0x1800016f2  cmp     edx, 1
0x1800016f5  jz      short loc_180001701
0x1800016f7  mov     eax, 1
0x1800016fc  add     rsp, 28h
0x180001700  retn
0x180001701  call    __scrt_dllmain_crt_thread_detach
0x180001706  jmp     short loc_18000170D
0x180001708  call    __scrt_dllmain_crt_thread_attach
0x18000170d  movzx   eax, al
0x180001710  add     rsp, 28h
0x180001714  retn
0x180001715  mov     rdx, r8
0x180001718  add     rsp, 28h
0x18000171c  jmp     dllmain_crt_process_attach
0x180001721  test    r8, r8
0x180001724  setnz   cl
0x180001727  add     rsp, 28h
0x18000172b  jmp     dllmain_crt_process_detach
```
