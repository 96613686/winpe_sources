# EfsRpcWriteFileRaw_Downlevel

- ea: `0x180007d00`
- end: `0x180007d64`
- name: `EfsRpcWriteFileRaw_Downlevel`
- size: `100`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, authz_impersonation`

## callees

- `0x180007d00`
- `0x180009b2c`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x180007d5d`
- `RPCRT4!RpcRaiseException` at `0x180007d5d`
- `RPCRT4!RpcImpersonateClient` at `0x180007d21`
- `RPCRT4!RpcImpersonateClient` at `0x180007d21`
- `RPCRT4!RpcRevertToSelf` at `0x180007d3a`
- `RPCRT4!RpcRevertToSelf` at `0x180007d3a`

## pseudocode

```c
__int64 __fastcall EfsRpcWriteFileRaw_Downlevel(__int64 a1, __int64 a2)
{
  RPC_STATUS v4; // ebx

  if ( !a2 || !a1 )
  {
    v4 = 5;
    goto LABEL_7;
  }
  v4 = RpcImpersonateClient(0);
  if ( v4 || (v4 = EfsWriteFileRaw(a1, a2), RpcRevertToSelf(), v4) )
LABEL_7:
    RpcRaiseException(v4);
  return 0;
}

```

## disassembly

```asm
0x180007d00  mov     [rsp+arg_0], rbx
0x180007d05  mov     [rsp+arg_8], rsi
0x180007d0a  push    rdi
0x180007d0b  sub     rsp, 20h
0x180007d0f  mov     rsi, rdx
0x180007d12  mov     rdi, rcx
0x180007d15  test    rdx, rdx
0x180007d18  jz      short loc_180007D56
0x180007d1a  test    rcx, rcx
0x180007d1d  jz      short loc_180007D56
0x180007d1f  xor     ecx, ecx; BindingHandle
0x180007d21  call    cs:__imp_RpcImpersonateClient
0x180007d27  mov     ebx, eax
0x180007d29  test    eax, eax
0x180007d2b  jnz     short loc_180007D5B
0x180007d2d  mov     rdx, rsi
0x180007d30  mov     rcx, rdi
0x180007d33  call    EfsWriteFileRaw
0x180007d38  mov     ebx, eax
0x180007d3a  call    cs:__imp_RpcRevertToSelf
0x180007d40  test    ebx, ebx
0x180007d42  jnz     short loc_180007D5B
0x180007d44  mov     rbx, [rsp+28h+arg_0]
0x180007d49  xor     eax, eax
0x180007d4b  mov     rsi, [rsp+28h+arg_8]
0x180007d50  add     rsp, 20h
0x180007d54  pop     rdi
0x180007d55  retn
0x180007d56  mov     ebx, 5
0x180007d5b  mov     ecx, ebx; exception
0x180007d5d  call    cs:__imp_RpcRaiseException
```
