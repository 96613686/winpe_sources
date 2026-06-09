# dllmain_crt_dispatch

- ea: `0x180006f70`
- end: `0x180006fc0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180007154`

## callees

- `0x180006f70`
- `0x180006fc8`
- `0x1800070c8`
- `0x180007498`
- `0x1800074c8`

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
0x180006f70  sub     rsp, 28h
0x180006f74  test    edx, edx
0x180006f76  jz      short loc_180006FB1
0x180006f78  sub     edx, 1
0x180006f7b  jz      short loc_180006FA5
0x180006f7d  sub     edx, 1
0x180006f80  jz      short loc_180006F98
0x180006f82  cmp     edx, 1
0x180006f85  jz      short loc_180006F91
0x180006f87  mov     eax, 1
0x180006f8c  add     rsp, 28h
0x180006f90  retn
0x180006f91  call    __scrt_dllmain_crt_thread_detach
0x180006f96  jmp     short loc_180006F9D
0x180006f98  call    __scrt_dllmain_crt_thread_attach
0x180006f9d  movzx   eax, al
0x180006fa0  add     rsp, 28h
0x180006fa4  retn
0x180006fa5  mov     rdx, r8
0x180006fa8  add     rsp, 28h
0x180006fac  jmp     dllmain_crt_process_attach
0x180006fb1  test    r8, r8
0x180006fb4  setnz   cl
0x180006fb7  add     rsp, 28h
0x180006fbb  jmp     dllmain_crt_process_detach
```
