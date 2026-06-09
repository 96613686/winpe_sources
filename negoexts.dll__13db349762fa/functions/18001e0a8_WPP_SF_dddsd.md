# WPP_SF_dddsd

- ea: `0x18001e0a8`
- end: `0x18001e12c`
- name: `WPP_SF_dddsd`
- size: `132`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180004404`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18001e11e`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18001e11e`

## string_xrefs

- `0x18001e0e3`: `onecore\ds\security\protocols\basessp\credapi.cxx`

## pseudocode

```c
ULONG WPP_SF_dddsd(TRACEHANDLE a1, __int64 a2, __int64 a3, int a4, ...)
{
  int v5[6]; // [rsp+80h] [rbp-18h] BYREF
  int v6; // [rsp+B8h] [rbp+20h] BYREF
  __int64 v7; // [rsp+C0h] [rbp+28h] BYREF
  va_list va; // [rsp+C0h] [rbp+28h]
  va_list va1; // [rsp+C8h] [rbp+30h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v7 = va_arg(va1, _QWORD);
  v6 = a4;
  v5[0] = 3091;
  return TraceMessage(
           a1,
           0x2Bu,
           &WPP_e2b939a1f5e739f8a467c1749fa620e3_Traceguids,
           0x1Du,
           &v6,
           4,
           va,
           4,
           va1,
           4,
           "onecore\\ds\\security\\protocols\\basessp\\credapi.cxx",
           50,
           v5,
           4,
           0);
}

```

## disassembly

```asm
0x18001e0a8  mov     r11, rsp
0x18001e0ab  mov     [r11+20h], r9d
0x18001e0af  sub     rsp, 98h
0x18001e0b6  mov     qword ptr [r11-28h], 0
0x18001e0be  lea     rax, [r11-18h]
0x18001e0c2  mov     r9d, 1Dh; MessageNumber
0x18001e0c8  mov     dword ptr [r11-18h], 0C13h
0x18001e0d0  lea     r8, WPP_e2b939a1f5e739f8a467c1749fa620e3_Traceguids; MessageGuid
0x18001e0d7  lea     edx, [r9-19h]
0x18001e0db  mov     [r11-30h], rdx
0x18001e0df  mov     [r11-38h], rax
0x18001e0e3  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\protocols\\bases"...
0x18001e0ea  mov     qword ptr [r11-40h], 32h ; '2'
0x18001e0f2  mov     [r11-48h], rax
0x18001e0f6  lea     rax, [r11+30h]
0x18001e0fa  mov     [r11-50h], rdx
0x18001e0fe  mov     [r11-58h], rax
0x18001e102  lea     rax, [r11+28h]
0x18001e106  mov     [r11-60h], rdx
0x18001e10a  mov     [r11-68h], rax
0x18001e10e  lea     rax, [r11+20h]
0x18001e112  mov     [r11-70h], rdx
0x18001e116  lea     edx, [r9+0Eh]; MessageFlags
0x18001e11a  mov     [r11-78h], rax
0x18001e11e  call    cs:__imp_TraceMessage
0x18001e124  add     rsp, 98h
0x18001e12b  retn
```
