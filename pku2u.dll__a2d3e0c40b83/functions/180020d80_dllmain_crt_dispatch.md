# dllmain_crt_dispatch

- ea: `0x180020d80`
- end: `0x180020dd0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180020f64`

## callees

- `0x180020d80`
- `0x180020dd8`
- `0x180020ed8`
- `0x1800212a8`
- `0x1800212d8`

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
0x180020d80  sub     rsp, 28h
0x180020d84  test    edx, edx
0x180020d86  jz      short loc_180020DC1
0x180020d88  sub     edx, 1
0x180020d8b  jz      short loc_180020DB5
0x180020d8d  sub     edx, 1
0x180020d90  jz      short loc_180020DA8
0x180020d92  cmp     edx, 1
0x180020d95  jz      short loc_180020DA1
0x180020d97  mov     eax, 1
0x180020d9c  add     rsp, 28h
0x180020da0  retn
0x180020da1  call    __scrt_dllmain_crt_thread_detach
0x180020da6  jmp     short loc_180020DAD
0x180020da8  call    __scrt_dllmain_crt_thread_attach
0x180020dad  movzx   eax, al
0x180020db0  add     rsp, 28h
0x180020db4  retn
0x180020db5  mov     rdx, r8
0x180020db8  add     rsp, 28h
0x180020dbc  jmp     dllmain_crt_process_attach
0x180020dc1  test    r8, r8
0x180020dc4  setnz   cl
0x180020dc7  add     rsp, 28h
0x180020dcb  jmp     dllmain_crt_process_detach
```
