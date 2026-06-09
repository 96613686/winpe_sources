# HnsRpc_OpenService

- ea: `0x18000c8a8`
- end: `0x18000c8d2`
- name: `HnsRpc_OpenService`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x1800026b8`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000c8c7`
- `RPCRT4!NdrClientCall3` at `0x18000c8c7`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HnsRpc_OpenService(__int64 a1, __int64 a2, __int64 a3)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x26u, 0, a1, a2, a3);
}

```

## disassembly

```asm
0x18000c8a8  sub     rsp, 38h
0x18000c8ac  mov     [rsp+38h+var_10], r8
0x18000c8b1  mov     r9, rcx
0x18000c8b4  xor     r8d, r8d; pReturnValue
0x18000c8b7  mov     [rsp+38h+var_18], rdx
0x18000c8bc  lea     rcx, pProxyInfo; pProxyInfo
0x18000c8c3  lea     edx, [r8+26h]; nProcNum
0x18000c8c7  call    cs:__imp_NdrClientCall3
0x18000c8cd  add     rsp, 38h
0x18000c8d1  retn
```
