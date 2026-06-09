# EfsRpcQueryRecoveryAgents

- ea: `0x18000c6d0`
- end: `0x18000c6fa`
- name: `EfsRpcQueryRecoveryAgents`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x18000bd78`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000c6ef`
- `RPCRT4!NdrClientCall3` at `0x18000c6ef`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall EfsRpcQueryRecoveryAgents(__int64 a1, __int64 a2, __int64 a3)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 7u, 0, a1, a2, a3);
}

```

## disassembly

```asm
0x18000c6d0  sub     rsp, 38h
0x18000c6d4  mov     [rsp+38h+var_10], r8
0x18000c6d9  mov     r9, rcx
0x18000c6dc  xor     r8d, r8d; pReturnValue
0x18000c6df  mov     [rsp+38h+var_18], rdx
0x18000c6e4  lea     rcx, pProxyInfo; pProxyInfo
0x18000c6eb  lea     edx, [r8+7]; nProcNum
0x18000c6ef  call    cs:__imp_NdrClientCall3
0x18000c6f5  add     rsp, 38h
0x18000c6f9  retn
```
