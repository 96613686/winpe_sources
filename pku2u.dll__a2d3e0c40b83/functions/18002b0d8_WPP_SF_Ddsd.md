# WPP_SF_Ddsd

- ea: `0x18002b0d8`
- end: `0x18002b150`
- name: `WPP_SF_Ddsd`
- size: `120`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18001b990`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18002b142`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18002b142`

## string_xrefs

- `0x18002b113`: `onecore\ds\security\protocols\pku2u\ctxtapi.cxx`

## pseudocode

```c
ULONG WPP_SF_Ddsd(TRACEHANDLE a1, __int64 a2, __int64 a3, int a4, ...)
{
  int v5[6]; // [rsp+70h] [rbp-18h] BYREF
  int v6; // [rsp+A8h] [rbp+20h] BYREF
  va_list va; // [rsp+B0h] [rbp+28h] BYREF

  va_start(va, a4);
  v6 = a4;
  v5[0] = 1771;
  return TraceMessage(
           a1,
           0x2Bu,
           &WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids,
           0x42u,
           &v6,
           4,
           va,
           4,
           "onecore\\ds\\security\\protocols\\pku2u\\ctxtapi.cxx",
           48,
           v5,
           4,
           0);
}

```

## disassembly

```asm
0x18002b0d8  mov     r11, rsp
0x18002b0db  mov     [r11+20h], r9d
0x18002b0df  sub     rsp, 88h
0x18002b0e6  mov     qword ptr [r11-28h], 0
0x18002b0ee  lea     rax, [r11-18h]
0x18002b0f2  mov     r9d, 42h ; 'B'; MessageNumber
0x18002b0f8  mov     [rsp+88h+var_18], 6EBh
0x18002b100  lea     r8, WPP_613b4c29aaec3b3a6c8fa9e74d2a7767_Traceguids; MessageGuid
0x18002b107  lea     edx, [r9-3Eh]
0x18002b10b  mov     [r11-30h], rdx
0x18002b10f  mov     [r11-38h], rax
0x18002b113  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\protocols\\pku2u"...
0x18002b11a  mov     qword ptr [r11-40h], 30h ; '0'
0x18002b122  mov     [r11-48h], rax
0x18002b126  lea     rax, [r11+28h]
0x18002b12a  mov     [r11-50h], rdx
0x18002b12e  mov     [r11-58h], rax
0x18002b132  lea     rax, [r11+20h]
0x18002b136  mov     [r11-60h], rdx
0x18002b13a  lea     edx, [r9-17h]; MessageFlags
0x18002b13e  mov     [r11-68h], rax
0x18002b142  call    cs:__imp_TraceMessage
0x18002b148  add     rsp, 88h
0x18002b14f  retn
```
