# WPP_SF_q

- ea: `0x180003ea0`
- end: `0x180003ede`
- name: `WPP_SF_q`
- size: `62`
- prototype: `ULONG(TRACEHANDLE, USHORT, __int64, ...)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180004b14`
- `0x180006a8c`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x180003ed3`
- `ADVAPI32!TraceMessage` at `0x180003ed3`

## pseudocode

```c
ULONG WPP_SF_q(TRACEHANDLE a1, USHORT a2, __int64 a3, ...)
{
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  return TraceMessage(a1, 0x2Bu, &WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids, a2, va, 8, 0);
}

```

## disassembly

```asm
0x180003ea0  mov     r11, rsp
0x180003ea3  mov     [r11+20h], r9
0x180003ea7  sub     rsp, 48h
0x180003eab  mov     qword ptr [r11-18h], 0
0x180003eb3  lea     rax, [r11+20h]
0x180003eb7  movzx   r9d, dx; MessageNumber
0x180003ebb  lea     r8, WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids; MessageGuid
0x180003ec2  mov     qword ptr [r11-20h], 8
0x180003eca  mov     edx, 2Bh ; '+'; MessageFlags
0x180003ecf  mov     [r11-28h], rax
0x180003ed3  call    cs:__imp_TraceMessage
0x180003ed9  add     rsp, 48h
0x180003edd  retn
```
