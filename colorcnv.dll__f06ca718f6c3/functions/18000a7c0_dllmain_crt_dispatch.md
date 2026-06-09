# dllmain_crt_dispatch

- ea: `0x18000a7c0`
- end: `0x18000a810`
- name: `dllmain_crt_dispatch`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x18000a9a4`

## callees

- `0x18000a7c0`
- `0x18000a818`
- `0x18000a918`
- `0x18000abe0`
- `0x18000ac10`

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
0x18000a7c0  sub     rsp, 28h
0x18000a7c4  test    edx, edx
0x18000a7c6  jz      short loc_18000A801
0x18000a7c8  sub     edx, 1
0x18000a7cb  jz      short loc_18000A7F5
0x18000a7cd  sub     edx, 1
0x18000a7d0  jz      short loc_18000A7E8
0x18000a7d2  cmp     edx, 1
0x18000a7d5  jz      short loc_18000A7E1
0x18000a7d7  mov     eax, 1
0x18000a7dc  add     rsp, 28h
0x18000a7e0  retn
0x18000a7e1  call    __scrt_dllmain_crt_thread_detach
0x18000a7e6  jmp     short loc_18000A7ED
0x18000a7e8  call    __scrt_dllmain_crt_thread_attach
0x18000a7ed  movzx   eax, al
0x18000a7f0  add     rsp, 28h
0x18000a7f4  retn
0x18000a7f5  mov     rdx, r8
0x18000a7f8  add     rsp, 28h
0x18000a7fc  jmp     dllmain_crt_process_attach
0x18000a801  test    r8, r8
0x18000a804  setnz   cl
0x18000a807  add     rsp, 28h
0x18000a80b  jmp     dllmain_crt_process_detach
```
