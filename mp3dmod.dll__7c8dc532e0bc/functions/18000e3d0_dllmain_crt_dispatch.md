# dllmain_crt_dispatch

- ea: `0x18000e3d0`
- end: `0x18000e420`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000e5b4`

## callees

- `0x18000e3d0`
- `0x18000e428`
- `0x18000e528`
- `0x18000e8d4`
- `0x18000e904`

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
0x18000e3d0  sub     rsp, 28h
0x18000e3d4  test    edx, edx
0x18000e3d6  jz      short loc_18000E411
0x18000e3d8  sub     edx, 1
0x18000e3db  jz      short loc_18000E405
0x18000e3dd  sub     edx, 1
0x18000e3e0  jz      short loc_18000E3F8
0x18000e3e2  cmp     edx, 1
0x18000e3e5  jz      short loc_18000E3F1
0x18000e3e7  mov     eax, 1
0x18000e3ec  add     rsp, 28h
0x18000e3f0  retn
0x18000e3f1  call    __scrt_dllmain_crt_thread_detach
0x18000e3f6  jmp     short loc_18000E3FD
0x18000e3f8  call    __scrt_dllmain_crt_thread_attach
0x18000e3fd  movzx   eax, al
0x18000e400  add     rsp, 28h
0x18000e404  retn
0x18000e405  mov     rdx, r8
0x18000e408  add     rsp, 28h
0x18000e40c  jmp     dllmain_crt_process_attach
0x18000e411  test    r8, r8
0x18000e414  setnz   cl
0x18000e417  add     rsp, 28h
0x18000e41b  jmp     dllmain_crt_process_detach
```
