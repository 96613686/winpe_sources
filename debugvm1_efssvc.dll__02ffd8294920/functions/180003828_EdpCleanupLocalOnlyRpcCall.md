# EdpCleanupLocalOnlyRpcCall

- ea: `0x180003828`
- end: `0x18000384c`
- name: `EdpCleanupLocalOnlyRpcCall`
- size: `36`
- prototype: ``
- caller_count: `22`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180003b80`
- `0x180003c30`
- `0x180003d70`
- `0x180003e50`
- `0x180003f20`
- `0x180004000`
- `0x1800040f0`
- `0x1800041d0`
- `0x180004290`
- `0x180004370`
- `0x1800044f0`
- `0x180004630`
- `0x180004800`
- `0x1800048b0`
- `0x180004a30`
- `0x180004af0`
- `0x180004f30`
- `0x180005030`
- `0x1800050f0`
- `0x1800052a0`
- `0x180007030`
- `0x180007bb0`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x180003845`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x180003831`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x180003831`
- `EFSCORE!EfsDllFreeUserInfo` at `0x18000383a`
- `EFSCORE!EfsDllFreeUserInfo` at `0x18000383a`

## pseudocode

```c
RPC_STATUS __fastcall EdpCleanupLocalOnlyRpcCall(__int64 a1)
{
  EfsDllUnloadUserProfile(a1);
  EfsDllFreeUserInfo(a1);
  return RpcRevertToSelf();
}

```

## disassembly

```asm
0x180003828  push    rbx
0x18000382a  sub     rsp, 20h
0x18000382e  mov     rbx, rcx
0x180003831  call    cs:__imp_EfsDllUnloadUserProfile
0x180003837  mov     rcx, rbx
0x18000383a  call    cs:__imp_EfsDllFreeUserInfo
0x180003840  add     rsp, 20h
0x180003844  pop     rbx
0x180003845  jmp     cs:__imp_RpcRevertToSelf
```
