# dllmain_crt_dispatch

- ea: `0x1800011e0`
- end: `0x180001230`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800013c4`

## callees

- `0x1800011e0`
- `0x180001238`
- `0x180001338`
- `0x180001624`
- `0x180001654`

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
0x1800011e0  sub     rsp, 28h
0x1800011e4  test    edx, edx
0x1800011e6  jz      short loc_180001221
0x1800011e8  sub     edx, 1
0x1800011eb  jz      short loc_180001215
0x1800011ed  sub     edx, 1
0x1800011f0  jz      short loc_180001208
0x1800011f2  cmp     edx, 1
0x1800011f5  jz      short loc_180001201
0x1800011f7  mov     eax, 1
0x1800011fc  add     rsp, 28h
0x180001200  retn
0x180001201  call    __scrt_dllmain_crt_thread_detach
0x180001206  jmp     short loc_18000120D
0x180001208  call    __scrt_dllmain_crt_thread_attach
0x18000120d  movzx   eax, al
0x180001210  add     rsp, 28h
0x180001214  retn
0x180001215  mov     rdx, r8
0x180001218  add     rsp, 28h
0x18000121c  jmp     dllmain_crt_process_attach
0x180001221  test    r8, r8
0x180001224  setnz   cl
0x180001227  add     rsp, 28h
0x18000122b  jmp     dllmain_crt_process_detach
```
