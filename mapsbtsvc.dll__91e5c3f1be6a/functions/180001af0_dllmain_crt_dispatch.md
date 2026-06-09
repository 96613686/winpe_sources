# dllmain_crt_dispatch

- ea: `0x180001af0`
- end: `0x180001b40`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001cd4`

## callees

- `0x180001af0`
- `0x180001b48`
- `0x180001c48`
- `0x180001f2c`
- `0x180001f5c`

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
0x180001af0  sub     rsp, 28h
0x180001af4  test    edx, edx
0x180001af6  jz      short loc_180001B31
0x180001af8  sub     edx, 1
0x180001afb  jz      short loc_180001B25
0x180001afd  sub     edx, 1
0x180001b00  jz      short loc_180001B18
0x180001b02  cmp     edx, 1
0x180001b05  jz      short loc_180001B11
0x180001b07  mov     eax, 1
0x180001b0c  add     rsp, 28h
0x180001b10  retn
0x180001b11  call    __scrt_dllmain_crt_thread_detach
0x180001b16  jmp     short loc_180001B1D
0x180001b18  call    __scrt_dllmain_crt_thread_attach
0x180001b1d  movzx   eax, al
0x180001b20  add     rsp, 28h
0x180001b24  retn
0x180001b25  mov     rdx, r8
0x180001b28  add     rsp, 28h
0x180001b2c  jmp     dllmain_crt_process_attach
0x180001b31  test    r8, r8
0x180001b34  setnz   cl
0x180001b37  add     rsp, 28h
0x180001b3b  jmp     dllmain_crt_process_detach
```
