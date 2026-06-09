# HnsRpc_ModifyGuestNetworkService

- ea: `0x18000c640`
- end: `0x18000c66a`
- name: `HnsRpc_ModifyGuestNetworkService`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000c65f`
- `RPCRT4!NdrClientCall3` at `0x18000c65f`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HnsRpc_ModifyGuestNetworkService(__int64 a1, __int64 a2, __int64 a3)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x2Eu, 0, a1, a2, a3);
}

```

## disassembly

```asm
0x18000c640  sub     rsp, 38h
0x18000c644  mov     [rsp+38h+var_10], r8
0x18000c649  mov     r9, rcx
0x18000c64c  xor     r8d, r8d; pReturnValue
0x18000c64f  mov     [rsp+38h+var_18], rdx
0x18000c654  lea     rcx, pProxyInfo; pProxyInfo
0x18000c65b  lea     edx, [r8+2Eh]; nProcNum
0x18000c65f  call    cs:__imp_NdrClientCall3
0x18000c665  add     rsp, 38h
0x18000c669  retn
```
