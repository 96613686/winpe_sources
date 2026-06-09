# dllmain_crt_dispatch

- ea: `0x1800011f0`
- end: `0x180001240`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800013d4`

## callees

- `0x1800011f0`
- `0x180001248`
- `0x180001348`
- `0x180001718`
- `0x180001748`

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
0x1800011f0  sub     rsp, 28h
0x1800011f4  test    edx, edx
0x1800011f6  jz      short loc_180001231
0x1800011f8  sub     edx, 1
0x1800011fb  jz      short loc_180001225
0x1800011fd  sub     edx, 1
0x180001200  jz      short loc_180001218
0x180001202  cmp     edx, 1
0x180001205  jz      short loc_180001211
0x180001207  mov     eax, 1
0x18000120c  add     rsp, 28h
0x180001210  retn
0x180001211  call    __scrt_dllmain_crt_thread_detach
0x180001216  jmp     short loc_18000121D
0x180001218  call    __scrt_dllmain_crt_thread_attach
0x18000121d  movzx   eax, al
0x180001220  add     rsp, 28h
0x180001224  retn
0x180001225  mov     rdx, r8
0x180001228  add     rsp, 28h
0x18000122c  jmp     dllmain_crt_process_attach
0x180001231  test    r8, r8
0x180001234  setnz   cl
0x180001237  add     rsp, 28h
0x18000123b  jmp     dllmain_crt_process_detach
```
