# CmsRpcClt_CreateContainer

- ea: `0x18000de44`
- end: `0x18000deab`
- name: `CmsRpcClt_CreateContainer`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180002b20`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000dea0`
- `RPCRT4!NdrClientCall3` at `0x18000dea0`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall CmsRpcClt_CreateContainer(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        __int64 a5,
        int a6,
        int a7,
        __int64 a8,
        __int64 a9)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0, 0, a1, a2, a3, a4, a5, a6, a7, a8, a9);
}

```

## disassembly

```asm
0x18000de44  mov     r11, rsp
0x18000de47  sub     rsp, 68h
0x18000de4b  mov     rax, [rsp+68h+arg_40]
0x18000de53  mov     [r11-10h], rax
0x18000de57  mov     rax, [rsp+68h+arg_38]
0x18000de5f  mov     [r11-18h], rax
0x18000de63  mov     eax, [rsp+68h+arg_30]
0x18000de6a  mov     [rsp+68h+var_20], eax
0x18000de6e  mov     eax, [rsp+68h+arg_28]
0x18000de75  mov     [rsp+68h+var_28], eax
0x18000de79  mov     rax, [rsp+68h+arg_20]
0x18000de81  mov     [r11-30h], rax
0x18000de85  mov     [r11-38h], r9
0x18000de89  mov     r9, rcx
0x18000de8c  mov     [r11-40h], r8d
0x18000de90  lea     rcx, pProxyInfo; pProxyInfo
0x18000de97  mov     [r11-48h], rdx
0x18000de9b  xor     r8d, r8d; pReturnValue
0x18000de9e  xor     edx, edx; nProcNum
0x18000dea0  call    cs:__imp_NdrClientCall3
0x18000dea6  add     rsp, 68h
0x18000deaa  retn
```
