# dllmain_crt_dispatch

- ea: `0x1800137b0`
- end: `0x180013800`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180013994`

## callees

- `0x1800137b0`
- `0x180013808`
- `0x180013908`
- `0x180013c68`
- `0x180013c98`

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
0x1800137b0  sub     rsp, 28h
0x1800137b4  test    edx, edx
0x1800137b6  jz      short loc_1800137F1
0x1800137b8  sub     edx, 1
0x1800137bb  jz      short loc_1800137E5
0x1800137bd  sub     edx, 1
0x1800137c0  jz      short loc_1800137D8
0x1800137c2  cmp     edx, 1
0x1800137c5  jz      short loc_1800137D1
0x1800137c7  mov     eax, 1
0x1800137cc  add     rsp, 28h
0x1800137d0  retn
0x1800137d1  call    __scrt_dllmain_crt_thread_detach
0x1800137d6  jmp     short loc_1800137DD
0x1800137d8  call    __scrt_dllmain_crt_thread_attach
0x1800137dd  movzx   eax, al
0x1800137e0  add     rsp, 28h
0x1800137e4  retn
0x1800137e5  mov     rdx, r8
0x1800137e8  add     rsp, 28h
0x1800137ec  jmp     dllmain_crt_process_attach
0x1800137f1  test    r8, r8
0x1800137f4  setnz   cl
0x1800137f7  add     rsp, 28h
0x1800137fb  jmp     dllmain_crt_process_detach
```
