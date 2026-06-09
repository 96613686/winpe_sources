# WPP_SF_ddsd

- ea: `0x1800159d8`
- end: `0x180015a50`
- name: `WPP_SF_ddsd`
- size: `120`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000a29c`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180015a42`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180015a42`

## string_xrefs

- `0x180015a13`: `onecore\ds\security\protocols\negoexts\ctxtapi.cxx`

## pseudocode

```c
ULONG WPP_SF_ddsd(TRACEHANDLE a1, __int64 a2, __int64 a3, int a4, ...)
{
  int v5[6]; // [rsp+70h] [rbp-18h] BYREF
  int v6; // [rsp+A8h] [rbp+20h] BYREF
  va_list va; // [rsp+B0h] [rbp+28h] BYREF

  va_start(va, a4);
  v6 = a4;
  v5[0] = 716;
  return TraceMessage(
           a1,
           0x2Bu,
           &WPP_6fa7dbc14d303f0b349d28a6dba66ee3_Traceguids,
           0x20u,
           &v6,
           4,
           va,
           4,
           "onecore\\ds\\security\\protocols\\negoexts\\ctxtapi.cxx",
           51,
           v5,
           4,
           0);
}

```

## disassembly

```asm
0x1800159d8  mov     r11, rsp
0x1800159db  mov     [r11+20h], r9d
0x1800159df  sub     rsp, 88h
0x1800159e6  mov     qword ptr [r11-28h], 0
0x1800159ee  lea     rax, [r11-18h]
0x1800159f2  mov     r9d, 20h ; ' '; MessageNumber
0x1800159f8  mov     [rsp+88h+var_18], 2CCh
0x180015a00  lea     r8, WPP_6fa7dbc14d303f0b349d28a6dba66ee3_Traceguids; MessageGuid
0x180015a07  lea     edx, [r9-1Ch]
0x180015a0b  mov     [r11-30h], rdx
0x180015a0f  mov     [r11-38h], rax
0x180015a13  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\protocols\\negoe"...
0x180015a1a  mov     qword ptr [r11-40h], 33h ; '3'
0x180015a22  mov     [r11-48h], rax
0x180015a26  lea     rax, [r11+28h]
0x180015a2a  mov     [r11-50h], rdx
0x180015a2e  mov     [r11-58h], rax
0x180015a32  lea     rax, [r11+20h]
0x180015a36  mov     [r11-60h], rdx
0x180015a3a  lea     edx, [r9+0Bh]; MessageFlags
0x180015a3e  mov     [r11-68h], rax
0x180015a42  call    cs:__imp_TraceMessage
0x180015a48  add     rsp, 88h
0x180015a4f  retn
```
