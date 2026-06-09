# EfsRpcFlushEfsCache_Downlevel

- ea: `0x1800079c0`
- end: `0x180007a0c`
- name: `EfsRpcFlushEfsCache_Downlevel`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x1800079c0`
- `0x180007d6c`
- `0x18000bc88`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x1800079e4`
- `RPCRT4!RpcImpersonateClient` at `0x1800079e4`
- `RPCRT4!RpcRevertToSelf` at `0x1800079f7`
- `RPCRT4!RpcRevertToSelf` at `0x1800079f7`

## pseudocode

```c
__int64 __fastcall EfsRpcFlushEfsCache_Downlevel(void *a1)
{
  unsigned __int16 *v1; // rdx
  CEfsClientBase *v2; // rcx
  unsigned int v3; // ebx
  int v5; // [rsp+38h] [rbp+10h] BYREF

  v5 = 0;
  if ( (unsigned int)EfsRpcpValidateClientCall(a1, &v5) || !v5 )
  {
    return 5;
  }
  else
  {
    v3 = RpcImpersonateClient(0);
    if ( !v3 )
    {
      v3 = CEfsClientBase::EfsFlushEfsCacheClient(v2, v1);
      RpcRevertToSelf();
    }
  }
  return v3;
}

```

## disassembly

```asm
0x1800079c0  push    rbx
0x1800079c2  sub     rsp, 20h
0x1800079c6  lea     rdx, [rsp+28h+arg_8]
0x1800079cb  mov     [rsp+28h+arg_8], 0
0x1800079d3  call    EfsRpcpValidateClientCall
0x1800079d8  test    eax, eax
0x1800079da  jnz     short loc_1800079FF
0x1800079dc  cmp     [rsp+28h+arg_8], eax
0x1800079e0  jz      short loc_1800079FF
0x1800079e2  xor     ecx, ecx; BindingHandle
0x1800079e4  call    cs:__imp_RpcImpersonateClient
0x1800079ea  mov     ebx, eax
0x1800079ec  test    eax, eax
0x1800079ee  jnz     short loc_180007A04
0x1800079f0  call    ?EfsFlushEfsCacheClient@CEfsClientBase@@QEAAKPEAG@Z; CEfsClientBase::EfsFlushEfsCacheClient(ushort *)
0x1800079f5  mov     ebx, eax
0x1800079f7  call    cs:__imp_RpcRevertToSelf
0x1800079fd  jmp     short loc_180007A04
0x1800079ff  mov     ebx, 5
0x180007a04  mov     eax, ebx
0x180007a06  add     rsp, 20h
0x180007a0a  pop     rbx
0x180007a0b  retn
```
