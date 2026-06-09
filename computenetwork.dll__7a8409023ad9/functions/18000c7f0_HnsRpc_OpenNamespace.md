# HnsRpc_OpenNamespace

- ea: `0x18000c7f0`
- end: `0x18000c81f`
- name: `HnsRpc_OpenNamespace`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000c814`
- `RPCRT4!NdrClientCall3` at `0x18000c814`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HnsRpc_OpenNamespace(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0xCu, 0, a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000c7f0  sub     rsp, 48h
0x18000c7f4  mov     [rsp+48h+var_18], r9
0x18000c7f9  mov     r9, rcx
0x18000c7fc  mov     [rsp+48h+var_20], r8
0x18000c801  lea     rcx, pProxyInfo; pProxyInfo
0x18000c808  xor     r8d, r8d; pReturnValue
0x18000c80b  mov     [rsp+48h+var_28], rdx
0x18000c810  lea     edx, [r8+0Ch]; nProcNum
0x18000c814  call    cs:__imp_NdrClientCall3
0x18000c81a  add     rsp, 48h
0x18000c81e  retn
```
