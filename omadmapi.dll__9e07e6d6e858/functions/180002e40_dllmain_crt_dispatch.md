# dllmain_crt_dispatch

- ea: `0x180002e40`
- end: `0x180002e90`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180003024`

## callees

- `0x180002e40`
- `0x180002e98`
- `0x180002f98`
- `0x180003368`
- `0x180003398`

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
0x180002e40  sub     rsp, 28h
0x180002e44  test    edx, edx
0x180002e46  jz      short loc_180002E81
0x180002e48  sub     edx, 1
0x180002e4b  jz      short loc_180002E75
0x180002e4d  sub     edx, 1
0x180002e50  jz      short loc_180002E68
0x180002e52  cmp     edx, 1
0x180002e55  jz      short loc_180002E61
0x180002e57  mov     eax, 1
0x180002e5c  add     rsp, 28h
0x180002e60  retn
0x180002e61  call    __scrt_dllmain_crt_thread_detach
0x180002e66  jmp     short loc_180002E6D
0x180002e68  call    __scrt_dllmain_crt_thread_attach
0x180002e6d  movzx   eax, al
0x180002e70  add     rsp, 28h
0x180002e74  retn
0x180002e75  mov     rdx, r8
0x180002e78  add     rsp, 28h
0x180002e7c  jmp     dllmain_crt_process_attach
0x180002e81  test    r8, r8
0x180002e84  setnz   cl
0x180002e87  add     rsp, 28h
0x180002e8b  jmp     dllmain_crt_process_detach
```
