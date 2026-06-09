# dllmain_crt_dispatch

- ea: `0x180013fc0`
- end: `0x180014010`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x1800141a4`

## callees

- `0x180013fc0`
- `0x180014018`
- `0x180014118`
- `0x180014884`
- `0x1800148b4`

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
0x180013fc0  sub     rsp, 28h
0x180013fc4  test    edx, edx
0x180013fc6  jz      short loc_180014001
0x180013fc8  sub     edx, 1
0x180013fcb  jz      short loc_180013FF5
0x180013fcd  sub     edx, 1
0x180013fd0  jz      short loc_180013FE8
0x180013fd2  cmp     edx, 1
0x180013fd5  jz      short loc_180013FE1
0x180013fd7  mov     eax, 1
0x180013fdc  add     rsp, 28h
0x180013fe0  retn
0x180013fe1  call    __scrt_dllmain_crt_thread_detach
0x180013fe6  jmp     short loc_180013FED
0x180013fe8  call    __scrt_dllmain_crt_thread_attach
0x180013fed  movzx   eax, al
0x180013ff0  add     rsp, 28h
0x180013ff4  retn
0x180013ff5  mov     rdx, r8
0x180013ff8  add     rsp, 28h
0x180013ffc  jmp     dllmain_crt_process_attach
0x180014001  test    r8, r8
0x180014004  setnz   cl
0x180014007  add     rsp, 28h
0x18001400b  jmp     dllmain_crt_process_detach
```
