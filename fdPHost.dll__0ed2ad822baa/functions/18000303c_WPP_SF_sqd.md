# WPP_SF_sqd

- ea: `0x18000303c`
- end: `0x180003099`
- name: `WPP_SF_sqd`
- size: `93`
- prototype: `ULONG(TRACEHANDLE, USHORT, __int64, __int64, ...)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180002020`
- `0x180002c8c`
- `0x180002d50`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000308e`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000308e`

## pseudocode

```c
ULONG WPP_SF_sqd(TRACEHANDLE a1, USHORT a2, __int64 a3, __int64 a4, ...)
{
  __int64 v5; // [rsp+90h] [rbp+28h] BYREF
  va_list va; // [rsp+90h] [rbp+28h]
  va_list va1; // [rsp+98h] [rbp+30h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v5 = va_arg(va1, _QWORD);
  return TraceMessage(a1, 0x2Bu, &WPP_a6e3756ed29831dc62ead4dd4235b941_Traceguids, a2, " ", 2, va, 8, va1, 4, 0);
}

```

## disassembly

```asm
0x18000303c  mov     r11, rsp
0x18000303f  sub     rsp, 68h
0x180003043  mov     qword ptr [r11-18h], 0
0x18000304b  lea     rax, [r11+30h]
0x18000304f  mov     qword ptr [r11-20h], 4
0x180003057  lea     r8, WPP_a6e3756ed29831dc62ead4dd4235b941_Traceguids; MessageGuid
0x18000305e  mov     [r11-28h], rax
0x180003062  lea     rax, [r11+28h]
0x180003066  mov     qword ptr [r11-30h], 8
0x18000306e  mov     [r11-38h], rax
0x180003072  lea     rax, asc_1800055C4; " "
0x180003079  movzx   r9d, dx; MessageNumber
0x18000307d  mov     edx, 2Bh ; '+'; MessageFlags
0x180003082  mov     qword ptr [r11-40h], 2
0x18000308a  mov     [r11-48h], rax
0x18000308e  call    cs:__imp_TraceMessage
0x180003094  add     rsp, 68h
0x180003098  retn
```
