# WPP_SF_sqP

- ea: `0x180002fd8`
- end: `0x180003033`
- name: `WPP_SF_sqP`
- size: `91`
- prototype: `ULONG(TRACEHANDLE, USHORT, __int64, __int64, ...)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180002bf0`
- `0x180002ec0`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180003028`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180003028`

## pseudocode

```c
ULONG WPP_SF_sqP(TRACEHANDLE a1, USHORT a2, __int64 a3, __int64 a4, ...)
{
  __int64 v5; // [rsp+90h] [rbp+28h] BYREF
  va_list va; // [rsp+90h] [rbp+28h]
  va_list va1; // [rsp+98h] [rbp+30h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v5 = va_arg(va1, _QWORD);
  return TraceMessage(a1, 0x2Bu, &WPP_a6e3756ed29831dc62ead4dd4235b941_Traceguids, a2, " ", 2, va, 8, va1, 8, 0);
}

```

## disassembly

```asm
0x180002fd8  mov     r11, rsp
0x180002fdb  sub     rsp, 68h
0x180002fdf  mov     qword ptr [r11-18h], 0
0x180002fe7  lea     rax, [r11+30h]
0x180002feb  mov     r8d, 8
0x180002ff1  movzx   r9d, dx; MessageNumber
0x180002ff5  mov     [r11-20h], r8
0x180002ff9  mov     edx, 2Bh ; '+'; MessageFlags
0x180002ffe  mov     [r11-28h], rax
0x180003002  lea     rax, [r11+28h]
0x180003006  mov     [r11-30h], r8
0x18000300a  lea     r8, WPP_a6e3756ed29831dc62ead4dd4235b941_Traceguids; MessageGuid
0x180003011  mov     [r11-38h], rax
0x180003015  lea     rax, asc_1800055C4; " "
0x18000301c  mov     qword ptr [r11-40h], 2
0x180003024  mov     [r11-48h], rax
0x180003028  call    cs:__imp_TraceMessage
0x18000302e  add     rsp, 68h
0x180003032  retn
```
