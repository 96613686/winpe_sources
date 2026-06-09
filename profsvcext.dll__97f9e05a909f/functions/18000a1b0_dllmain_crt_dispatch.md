# dllmain_crt_dispatch

- ea: `0x18000a1b0`
- end: `0x18000a200`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000a394`

## callees

- `0x18000a1b0`
- `0x18000a208`
- `0x18000a308`
- `0x18000a5d0`
- `0x18000a600`

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
0x18000a1b0  sub     rsp, 28h
0x18000a1b4  test    edx, edx
0x18000a1b6  jz      short loc_18000A1F1
0x18000a1b8  sub     edx, 1
0x18000a1bb  jz      short loc_18000A1E5
0x18000a1bd  sub     edx, 1
0x18000a1c0  jz      short loc_18000A1D8
0x18000a1c2  cmp     edx, 1
0x18000a1c5  jz      short loc_18000A1D1
0x18000a1c7  mov     eax, 1
0x18000a1cc  add     rsp, 28h
0x18000a1d0  retn
0x18000a1d1  call    __scrt_dllmain_crt_thread_detach
0x18000a1d6  jmp     short loc_18000A1DD
0x18000a1d8  call    __scrt_dllmain_crt_thread_attach
0x18000a1dd  movzx   eax, al
0x18000a1e0  add     rsp, 28h
0x18000a1e4  retn
0x18000a1e5  mov     rdx, r8
0x18000a1e8  add     rsp, 28h
0x18000a1ec  jmp     dllmain_crt_process_attach
0x18000a1f1  test    r8, r8
0x18000a1f4  setnz   cl
0x18000a1f7  add     rsp, 28h
0x18000a1fb  jmp     dllmain_crt_process_detach
```
