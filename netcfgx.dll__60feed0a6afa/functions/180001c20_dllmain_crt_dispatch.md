# dllmain_crt_dispatch

- ea: `0x180001c20`
- end: `0x180001c70`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001e04`

## callees

- `0x180001c20`
- `0x180001c78`
- `0x180001d78`
- `0x1800020ac`
- `0x1800020dc`

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
0x180001c20  sub     rsp, 28h
0x180001c24  test    edx, edx
0x180001c26  jz      short loc_180001C61
0x180001c28  sub     edx, 1
0x180001c2b  jz      short loc_180001C55
0x180001c2d  sub     edx, 1
0x180001c30  jz      short loc_180001C48
0x180001c32  cmp     edx, 1
0x180001c35  jz      short loc_180001C41
0x180001c37  mov     eax, 1
0x180001c3c  add     rsp, 28h
0x180001c40  retn
0x180001c41  call    __scrt_dllmain_crt_thread_detach
0x180001c46  jmp     short loc_180001C4D
0x180001c48  call    __scrt_dllmain_crt_thread_attach
0x180001c4d  movzx   eax, al
0x180001c50  add     rsp, 28h
0x180001c54  retn
0x180001c55  mov     rdx, r8
0x180001c58  add     rsp, 28h
0x180001c5c  jmp     dllmain_crt_process_attach
0x180001c61  test    r8, r8
0x180001c64  setnz   cl
0x180001c67  add     rsp, 28h
0x180001c6b  jmp     dllmain_crt_process_detach
```
