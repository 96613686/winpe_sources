# WPP_SF_sd

- ea: `0x18000e9e8`
- end: `0x18000ea35`
- name: `WPP_SF_sd`
- size: `77`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180003a10`
- `0x180004404`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000ea2a`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000ea2a`

## string_xrefs

- `0x18000ea0e`: `onecore\ds\security\protocols\basessp\credapi.cxx`

## pseudocode

```c
ULONG WPP_SF_sd(TRACEHANDLE a1, USHORT a2, __int64 a3, __int64 a4, ...)
{
  va_list va; // [rsp+80h] [rbp+28h] BYREF

  va_start(va, a4);
  return TraceMessage(
           a1,
           0x2Bu,
           &WPP_e2b939a1f5e739f8a467c1749fa620e3_Traceguids,
           a2,
           "onecore\\ds\\security\\protocols\\basessp\\credapi.cxx",
           50,
           va,
           4,
           0);
}

```

## disassembly

```asm
0x18000e9e8  mov     r11, rsp
0x18000e9eb  sub     rsp, 58h
0x18000e9ef  mov     qword ptr [r11-18h], 0
0x18000e9f7  lea     rax, [r11+28h]
0x18000e9fb  mov     qword ptr [r11-20h], 4
0x18000ea03  lea     r8, WPP_e2b939a1f5e739f8a467c1749fa620e3_Traceguids; MessageGuid
0x18000ea0a  mov     [r11-28h], rax
0x18000ea0e  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\protocols\\bases"...
0x18000ea15  movzx   r9d, dx; MessageNumber
0x18000ea19  mov     edx, 2Bh ; '+'; MessageFlags
0x18000ea1e  mov     qword ptr [r11-30h], 32h ; '2'
0x18000ea26  mov     [r11-38h], rax
0x18000ea2a  call    cs:__imp_TraceMessage
0x18000ea30  add     rsp, 58h
0x18000ea34  retn
```
