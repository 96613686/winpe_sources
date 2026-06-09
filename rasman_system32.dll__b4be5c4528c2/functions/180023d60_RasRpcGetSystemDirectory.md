# RasRpcGetSystemDirectory

- ea: `0x180023d60`
- end: `0x180023d91`
- name: `RasRpcGetSystemDirectory`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18002464c`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180023d7f`
- `RPCRT4!NdrClientCall3` at `0x180023d7f`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall RasRpcGetSystemDirectory(__int64 a1, __int64 a2, int a3)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0xBu, 0, a1, a2, a3);
}

```

## disassembly

```asm
0x180023d60  sub     rsp, 38h
0x180023d64  mov     [rsp+38h+var_10], r8d
0x180023d69  mov     r9, rcx
0x180023d6c  xor     r8d, r8d; pReturnValue
0x180023d6f  mov     [rsp+38h+var_18], rdx
0x180023d74  lea     rcx, pProxyInfo; pProxyInfo
0x180023d7b  lea     edx, [r8+0Bh]; nProcNum
0x180023d7f  call    cs:__imp_NdrClientCall3
0x180023d86  nop     dword ptr [rax+rax+00h]
0x180023d8b  add     rsp, 38h
0x180023d8f  retn
```
