# dllmain_crt_dispatch

- ea: `0x180023eb0`
- end: `0x180023f00`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180024094`

## callees

- `0x180023eb0`
- `0x180023f08`
- `0x180024008`
- `0x1800242d0`
- `0x180024300`

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
0x180023eb0  sub     rsp, 28h
0x180023eb4  test    edx, edx
0x180023eb6  jz      short loc_180023EF1
0x180023eb8  sub     edx, 1
0x180023ebb  jz      short loc_180023EE5
0x180023ebd  sub     edx, 1
0x180023ec0  jz      short loc_180023ED8
0x180023ec2  cmp     edx, 1
0x180023ec5  jz      short loc_180023ED1
0x180023ec7  mov     eax, 1
0x180023ecc  add     rsp, 28h
0x180023ed0  retn
0x180023ed1  call    __scrt_dllmain_crt_thread_detach
0x180023ed6  jmp     short loc_180023EDD
0x180023ed8  call    __scrt_dllmain_crt_thread_attach
0x180023edd  movzx   eax, al
0x180023ee0  add     rsp, 28h
0x180023ee4  retn
0x180023ee5  mov     rdx, r8
0x180023ee8  add     rsp, 28h
0x180023eec  jmp     dllmain_crt_process_attach
0x180023ef1  test    r8, r8
0x180023ef4  setnz   cl
0x180023ef7  add     rsp, 28h
0x180023efb  jmp     dllmain_crt_process_detach
```
