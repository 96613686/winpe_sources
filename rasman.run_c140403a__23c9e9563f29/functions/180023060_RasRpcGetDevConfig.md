# RasRpcGetDevConfig

- ea: `0x180023060`
- end: `0x180023098`
- name: `RasRpcGetDevConfig`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180023aa0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18002308d`
- `RPCRT4!NdrClientCall3` at `0x18002308d`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall RasRpcGetDevConfig(__int64 a1, int a2, __int64 a3, __int64 a4, __int64 a5)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 2u, 0, a1, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x180023060  sub     rsp, 48h
0x180023064  mov     rax, [rsp+48h+arg_20]
0x180023069  mov     [rsp+48h+var_10], rax
0x18002306e  mov     [rsp+48h+var_18], r9
0x180023073  mov     r9, rcx
0x180023076  mov     [rsp+48h+var_20], r8
0x18002307b  lea     rcx, pProxyInfo; pProxyInfo
0x180023082  xor     r8d, r8d; pReturnValue
0x180023085  mov     [rsp+48h+var_28], edx
0x180023089  lea     edx, [r8+2]; nProcNum
0x18002308d  call    cs:__imp_NdrClientCall3
0x180023093  add     rsp, 48h
0x180023097  retn
```
