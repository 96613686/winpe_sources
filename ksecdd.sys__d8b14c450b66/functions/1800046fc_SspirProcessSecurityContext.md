# SspirProcessSecurityContext

- ea: `0x1800046fc`
- end: `0x180004807`
- name: `SspirProcessSecurityContext`
- size: `267`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, int, int, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180002a84`

## import_xrefs

- `msrpc!NdrClientCall3` at `0x1800047f2`
- `msrpc!NdrClientCall3` at `0x1800047f2`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall SspirProcessSecurityContext(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7,
        int a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        __int64 a16,
        __int64 a17,
        __int64 a18,
        __int64 a19,
        __int64 a20,
        __int64 a21)
{
  return NdrClientCall3(
           (MIDL_STUBLESS_PROXY_INFO *)&sspirpc_ProxyInfo,
           6u,
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
           a13,
           a14,
           a15,
           a16,
           a17,
           a18,
           a19,
           a20,
           a21);
}

```

## disassembly

```asm
0x1800046fc  mov     r11, rsp
0x1800046ff  sub     rsp, 0C8h
0x180004706  mov     rax, [rsp+0C8h+arg_A0]
0x18000470e  mov     [r11-10h], rax
0x180004712  mov     rax, [rsp+0C8h+arg_98]
0x18000471a  mov     [r11-18h], rax
0x18000471e  mov     rax, [rsp+0C8h+arg_90]
0x180004726  mov     [r11-20h], rax
0x18000472a  mov     rax, [rsp+0C8h+arg_88]
0x180004732  mov     [r11-28h], rax
0x180004736  mov     rax, [rsp+0C8h+arg_80]
0x18000473e  mov     [r11-30h], rax
0x180004742  mov     rax, [rsp+0C8h+arg_78]
0x18000474a  mov     [r11-38h], rax
0x18000474e  mov     rax, [rsp+0C8h+arg_70]
0x180004756  mov     [r11-40h], rax
0x18000475a  mov     rax, [rsp+0C8h+arg_68]
0x180004762  mov     [r11-48h], rax
0x180004766  mov     rax, [rsp+0C8h+arg_60]
0x18000476e  mov     [r11-50h], rax
0x180004772  mov     rax, [rsp+0C8h+arg_58]
0x18000477a  mov     [r11-58h], rax
0x18000477e  mov     rax, [rsp+0C8h+arg_50]
0x180004786  mov     [r11-60h], rax
0x18000478a  mov     rax, [rsp+0C8h+arg_48]
0x180004792  mov     [r11-68h], rax
0x180004796  mov     rax, [rsp+0C8h+arg_40]
0x18000479e  mov     [r11-70h], rax
0x1800047a2  mov     eax, [rsp+0C8h+arg_38]
0x1800047a9  mov     [rsp+0C8h+var_78], eax
0x1800047ad  mov     eax, [rsp+0C8h+arg_30]
0x1800047b4  mov     [rsp+0C8h+var_80], eax
0x1800047b8  mov     rax, [rsp+0C8h+arg_28]
0x1800047c0  mov     [rsp+0C8h+var_88], rax
0x1800047c5  mov     rax, [rsp+0C8h+arg_20]
0x1800047cd  mov     [rsp+0C8h+var_90], rax
0x1800047d2  mov     [rsp+0C8h+var_98], r9
0x1800047d7  mov     r9, rcx
0x1800047da  mov     [rsp+0C8h+var_A0], r8
0x1800047df  lea     rcx, ?sspirpc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800047e6  xor     r8d, r8d; pReturnValue
0x1800047e9  mov     [rsp+0C8h+var_A8], rdx
0x1800047ee  lea     edx, [r8+6]; nProcNum
0x1800047f2  call    cs:__imp_NdrClientCall3
0x1800047f9  nop     dword ptr [rax+rax+00h]
0x1800047fe  add     rsp, 0C8h
0x180004805  retn
```
