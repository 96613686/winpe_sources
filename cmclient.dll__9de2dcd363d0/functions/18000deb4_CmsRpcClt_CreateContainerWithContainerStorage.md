# CmsRpcClt_CreateContainerWithContainerStorage

- ea: `0x18000deb4`
- end: `0x18000df1d`
- name: `CmsRpcClt_CreateContainerWithContainerStorage`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180002244`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000df12`
- `RPCRT4!NdrClientCall3` at `0x18000df12`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall CmsRpcClt_CreateContainerWithContainerStorage(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        int a7,
        __int64 a8,
        __int64 a9)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 1u, 0, a1, a2, a3, a4, a5, a6, a7, a8, a9);
}

```

## disassembly

```asm
0x18000deb4  mov     r11, rsp
0x18000deb7  sub     rsp, 68h
0x18000debb  mov     rax, [rsp+68h+arg_40]
0x18000dec3  mov     [r11-10h], rax
0x18000dec7  mov     rax, [rsp+68h+arg_38]
0x18000decf  mov     [r11-18h], rax
0x18000ded3  mov     eax, [rsp+68h+arg_30]
0x18000deda  mov     [rsp+68h+var_20], eax
0x18000dede  mov     eax, [rsp+68h+arg_28]
0x18000dee5  mov     [rsp+68h+var_28], eax
0x18000dee9  mov     rax, [rsp+68h+arg_20]
0x18000def1  mov     [r11-30h], rax
0x18000def5  mov     [r11-38h], r9
0x18000def9  mov     r9, rcx
0x18000defc  mov     [r11-40h], r8
0x18000df00  lea     rcx, pProxyInfo; pProxyInfo
0x18000df07  xor     r8d, r8d; pReturnValue
0x18000df0a  mov     [rsp+68h+var_48], edx
0x18000df0e  lea     edx, [r8+1]; nProcNum
0x18000df12  call    cs:__imp_NdrClientCall3
0x18000df18  add     rsp, 68h
0x18000df1c  retn
```
