# RasRpcDeleteEntry

- ea: `0x180023b40`
- end: `0x180023b71`
- name: `RasRpcDeleteEntry`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180024764`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180023b5f`
- `RPCRT4!NdrClientCall3` at `0x180023b5f`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall RasRpcDeleteEntry(__int64 a1, __int64 a2, __int64 a3)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 5u, 0, a1, a2, a3);
}

```

## disassembly

```asm
0x180023b40  sub     rsp, 38h
0x180023b44  mov     [rsp+38h+var_10], r8
0x180023b49  mov     r9, rcx
0x180023b4c  xor     r8d, r8d; pReturnValue
0x180023b4f  mov     [rsp+38h+var_18], rdx
0x180023b54  lea     rcx, pProxyInfo; pProxyInfo
0x180023b5b  lea     edx, [r8+5]; nProcNum
0x180023b5f  call    cs:__imp_NdrClientCall3
0x180023b66  nop     dword ptr [rax+rax+00h]
0x180023b6b  add     rsp, 38h
0x180023b6f  retn
```
