# dllmain_crt_dispatch

- ea: `0x180001b80`
- end: `0x180001bd0`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001d64`

## callees

- `0x180001b80`
- `0x180001bd8`
- `0x180001cd8`
- `0x180001fdc`
- `0x18000200c`

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
0x180001b80  sub     rsp, 28h
0x180001b84  test    edx, edx
0x180001b86  jz      short loc_180001BC1
0x180001b88  sub     edx, 1
0x180001b8b  jz      short loc_180001BB5
0x180001b8d  sub     edx, 1
0x180001b90  jz      short loc_180001BA8
0x180001b92  cmp     edx, 1
0x180001b95  jz      short loc_180001BA1
0x180001b97  mov     eax, 1
0x180001b9c  add     rsp, 28h
0x180001ba0  retn
0x180001ba1  call    __scrt_dllmain_crt_thread_detach
0x180001ba6  jmp     short loc_180001BAD
0x180001ba8  call    __scrt_dllmain_crt_thread_attach
0x180001bad  movzx   eax, al
0x180001bb0  add     rsp, 28h
0x180001bb4  retn
0x180001bb5  mov     rdx, r8
0x180001bb8  add     rsp, 28h
0x180001bbc  jmp     dllmain_crt_process_attach
0x180001bc1  test    r8, r8
0x180001bc4  setnz   cl
0x180001bc7  add     rsp, 28h
0x180001bcb  jmp     dllmain_crt_process_detach
```
