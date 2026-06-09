# RasRpcGetDevConfig

- ea: `0x180023c60`
- end: `0x180023c9f`
- name: `RasRpcGetDevConfig`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180024788`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180023c8d`
- `RPCRT4!NdrClientCall3` at `0x180023c8d`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall RasRpcGetDevConfig(__int64 a1, int a2, __int64 a3, __int64 a4, __int64 a5)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 2u, 0, a1, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x180023c60  sub     rsp, 48h
0x180023c64  mov     rax, [rsp+48h+arg_20]
0x180023c69  mov     [rsp+48h+var_10], rax
0x180023c6e  mov     [rsp+48h+var_18], r9
0x180023c73  mov     r9, rcx
0x180023c76  mov     [rsp+48h+var_20], r8
0x180023c7b  lea     rcx, pProxyInfo; pProxyInfo
0x180023c82  xor     r8d, r8d; pReturnValue
0x180023c85  mov     [rsp+48h+var_28], edx
0x180023c89  lea     edx, [r8+2]; nProcNum
0x180023c8d  call    cs:__imp_NdrClientCall3
0x180023c94  nop     dword ptr [rax+rax+00h]
0x180023c99  add     rsp, 48h
0x180023c9d  retn
```
