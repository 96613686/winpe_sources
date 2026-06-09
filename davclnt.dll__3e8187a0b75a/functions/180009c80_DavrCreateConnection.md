# DavrCreateConnection

- ea: `0x180009c80`
- end: `0x180009d50`
- name: `DavrCreateConnection`
- size: `208`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64, __int64, __int64, int, __int64, int, __int64, int, int, __int64, __int64, int, unsigned __int8, unsigned __int8, int, __int64)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180007ad0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180009d42`
- `RPCRT4!NdrClientCall3` at `0x180009d42`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall DavrCreateConnection(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        int a6,
        __int64 a7,
        int a8,
        int a9,
        __int64 a10,
        __int64 a11,
        int a12,
        unsigned __int8 a13,
        unsigned __int8 a14,
        int a15,
        __int64 a16)
{
  int v22; // [rsp+78h] [rbp-30h]
  int v23; // [rsp+80h] [rbp-28h]

  v23 = a14;
  v22 = a13;
  return NdrClientCall3(
           (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
           0,
           0,
           a1,
           a2,
           a3,
           a4,
           a5,
           a6,
           a7,
           a8,
           a9,
           a10,
           a11,
           a12,
           v22,
           v23,
           a15,
           a16);
}

```

## disassembly

```asm
0x180009c80  sub     rsp, 0A8h
0x180009c87  mov     rax, [rsp+0A8h+arg_78]
0x180009c8f  movzx   r10d, [rsp+0A8h+arg_68]
0x180009c98  movzx   r11d, [rsp+0A8h+arg_60]
0x180009ca1  mov     [rsp+0A8h+var_18], rax
0x180009ca9  mov     eax, [rsp+0A8h+arg_70]
0x180009cb0  mov     [rsp+0A8h+var_20], eax
0x180009cb7  mov     eax, [rsp+0A8h+arg_58]
0x180009cbe  mov     [rsp+0A8h+var_28], r10d
0x180009cc6  mov     [rsp+0A8h+var_30], r11d
0x180009ccb  mov     [rsp+0A8h+var_38], eax
0x180009ccf  mov     rax, [rsp+0A8h+arg_50]
0x180009cd7  mov     [rsp+0A8h+var_40], rax
0x180009cdc  mov     rax, [rsp+0A8h+arg_48]
0x180009ce4  mov     [rsp+0A8h+var_48], rax
0x180009ce9  mov     eax, [rsp+0A8h+arg_40]
0x180009cf0  mov     [rsp+0A8h+var_50], eax
0x180009cf4  mov     eax, [rsp+0A8h+arg_38]
0x180009cfb  mov     [rsp+0A8h+var_58], eax
0x180009cff  mov     rax, [rsp+0A8h+arg_30]
0x180009d07  mov     [rsp+0A8h+var_60], rax
0x180009d0c  mov     eax, [rsp+0A8h+arg_28]
0x180009d13  mov     [rsp+0A8h+var_68], eax
0x180009d17  mov     rax, [rsp+0A8h+arg_20]
0x180009d1f  mov     [rsp+0A8h+var_70], rax
0x180009d24  mov     [rsp+0A8h+var_78], r9d
0x180009d29  mov     r9, rcx
0x180009d2c  mov     [rsp+0A8h+var_80], r8
0x180009d31  lea     rcx, pProxyInfo; pProxyInfo
0x180009d38  mov     [rsp+0A8h+var_88], rdx
0x180009d3d  xor     r8d, r8d; pReturnValue
0x180009d40  xor     edx, edx; nProcNum
0x180009d42  call    cs:__imp_NdrClientCall3
0x180009d48  add     rsp, 0A8h
0x180009d4f  retn
```
