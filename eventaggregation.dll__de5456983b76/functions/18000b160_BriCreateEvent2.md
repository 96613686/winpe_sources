# BriCreateEvent2

- ea: `0x18000b160`
- end: `0x18000b1f2`
- name: `BriCreateEvent2`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800022b0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000b1e4`
- `RPCRT4!NdrClientCall3` at `0x18000b1e4`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall BriCreateEvent2(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12)
{
  return NdrClientCall3(
           (MIDL_STUBLESS_PROXY_INFO *)&stru_18000D0F0,
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
           a12);
}

```

## disassembly

```asm
0x18000b160  mov     r11, rsp
0x18000b163  sub     rsp, 88h
0x18000b16a  mov     rax, [rsp+88h+arg_58]
0x18000b172  mov     [r11-18h], rax
0x18000b176  mov     rax, [rsp+88h+arg_50]
0x18000b17e  mov     [r11-20h], rax
0x18000b182  mov     rax, [rsp+88h+arg_48]
0x18000b18a  mov     [r11-28h], rax
0x18000b18e  mov     rax, [rsp+88h+arg_40]
0x18000b196  mov     [r11-30h], rax
0x18000b19a  mov     rax, [rsp+88h+arg_38]
0x18000b1a2  mov     [r11-38h], rax
0x18000b1a6  mov     eax, [rsp+88h+arg_30]
0x18000b1ad  mov     [rsp+88h+var_40], eax
0x18000b1b1  mov     rax, [rsp+88h+arg_28]
0x18000b1b9  mov     [r11-48h], rax
0x18000b1bd  mov     rax, [rsp+88h+arg_20]
0x18000b1c5  mov     [r11-50h], rax
0x18000b1c9  mov     [r11-58h], r9
0x18000b1cd  mov     r9, rcx
0x18000b1d0  mov     [r11-60h], r8d
0x18000b1d4  lea     rcx, stru_18000D0F0; pProxyInfo
0x18000b1db  mov     [r11-68h], rdx
0x18000b1df  xor     r8d, r8d; pReturnValue
0x18000b1e2  xor     edx, edx; nProcNum
0x18000b1e4  call    cs:__imp_NdrClientCall3
0x18000b1ea  add     rsp, 88h
0x18000b1f1  retn
```
