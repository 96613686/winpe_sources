# EfsRpcReadFileRaw

- ea: `0x1800074a0`
- end: `0x180007526`
- name: `EfsRpcReadFileRaw`
- size: `134`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callees

- `0x1800037b8`
- `0x1800074a0`
- `0x18000bf0c`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x180007519`
- `RPCRT4!RpcRaiseException` at `0x180007519`
- `EFSCORE!EfsDllReadFileRaw` at `0x1800074ef`
- `EFSCORE!EfsDllReadFileRaw` at `0x1800074ef`

## pseudocode

```c
__int64 __fastcall EfsRpcReadFileRaw(__int64 a1, __int64 a2)
{
  unsigned int v4; // eax
  __int64 v5; // rcx
  RPC_STATUS v6; // ebx
  __int64 result; // rax

  if ( !a2 || !a1 )
  {
    v6 = 5;
    goto LABEL_8;
  }
  v4 = EfsEnforceClientAuthentication();
  v6 = v4;
  if ( v4 )
  {
    fnEfsLogTrace1(v5, (__int64)EFS_API_ERROR, v4, 6, 45);
    goto LABEL_8;
  }
  result = EfsDllReadFileRaw(a1, a2);
  v6 = result;
  if ( (_DWORD)result )
LABEL_8:
    RpcRaiseException(v6);
  return result;
}

```

## disassembly

```asm
0x1800074a0  mov     [rsp+arg_0], rbx
0x1800074a5  mov     [rsp+arg_8], rsi
0x1800074aa  push    rdi
0x1800074ab  sub     rsp, 30h
0x1800074af  mov     rsi, rdx
0x1800074b2  mov     rdi, rcx
0x1800074b5  test    rdx, rdx
0x1800074b8  jz      short loc_180007512
0x1800074ba  test    rcx, rcx
0x1800074bd  jz      short loc_180007512
0x1800074bf  call    EfsEnforceClientAuthentication
0x1800074c4  mov     ebx, eax
0x1800074c6  test    eax, eax
0x1800074c8  jz      short loc_1800074E9
0x1800074ca  mov     r9d, 6
0x1800074d0  mov     [rsp+38h+var_18], 12Dh
0x1800074d8  mov     r8d, eax
0x1800074db  lea     rdx, EFS_API_ERROR
0x1800074e2  call    fnEfsLogTrace1
0x1800074e7  jmp     short loc_180007517
0x1800074e9  mov     rdx, rsi
0x1800074ec  mov     rcx, rdi
0x1800074ef  call    cs:__imp_EfsDllReadFileRaw
0x1800074f6  nop     dword ptr [rax+rax+00h]
0x1800074fb  mov     ebx, eax
0x1800074fd  test    eax, eax
0x1800074ff  jnz     short loc_180007517
0x180007501  mov     rbx, [rsp+38h+arg_0]
0x180007506  mov     rsi, [rsp+38h+arg_8]
0x18000750b  add     rsp, 30h
0x18000750f  pop     rdi
0x180007510  retn
0x180007512  mov     ebx, 5
0x180007517  mov     ecx, ebx; exception
0x180007519  call    cs:__imp_RpcRaiseException
0x180007520  nop     dword ptr [rax+rax+00h]
0x180007525  int     3; Trap to Debugger
```
