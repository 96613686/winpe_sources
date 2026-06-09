# WPP_SF_q

- ea: `0x18000eb00`
- end: `0x18000eb3e`
- name: `WPP_SF_q`
- size: `62`
- prototype: `ULONG(TRACEHANDLE, USHORT, __int64, ...)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000e470`
- `0x18000e520`
- `0x18000e5d0`
- `0x18000e740`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x18000eb33`
- `ADVAPI32!TraceMessage` at `0x18000eb33`

## pseudocode

```c
ULONG WPP_SF_q(TRACEHANDLE a1, USHORT a2, __int64 a3, ...)
{
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  return TraceMessage(a1, 0x2Bu, &WPP_efece49b8938379c060169b7945fb4b7_Traceguids, a2, va, 8, 0);
}

```

## disassembly

```asm
0x18000eb00  mov     r11, rsp
0x18000eb03  mov     [r11+20h], r9
0x18000eb07  sub     rsp, 48h
0x18000eb0b  mov     qword ptr [r11-18h], 0
0x18000eb13  lea     rax, [r11+20h]
0x18000eb17  movzx   r9d, dx; MessageNumber
0x18000eb1b  lea     r8, WPP_efece49b8938379c060169b7945fb4b7_Traceguids; MessageGuid
0x18000eb22  mov     qword ptr [r11-20h], 8
0x18000eb2a  mov     edx, 2Bh ; '+'; MessageFlags
0x18000eb2f  mov     [r11-28h], rax
0x18000eb33  call    cs:__imp_TraceMessage
0x18000eb39  add     rsp, 48h
0x18000eb3d  retn
```
