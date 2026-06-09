# WPP_SF_sd

- ea: `0x18000bc98`
- end: `0x18000bcde`
- name: `WPP_SF_sd`
- size: `70`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a9e8`
- `0x18000e340`
- `0x18000e540`
- `0x18000e6e0`
- `0x18000ebc8`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x18000bcd3`
- `ADVAPI32!TraceMessage` at `0x18000bcd3`

## pseudocode

```c
ULONG WPP_SF_sd(TRACEHANDLE a1, USHORT a2, const GUID *a3, __int64 a4, ...)
{
  va_list va; // [rsp+80h] [rbp+28h] BYREF

  va_start(va, a4);
  return TraceMessage(a1, 0x2Bu, a3, a2, " ", 2, va, 4, 0);
}

```

## disassembly

```asm
0x18000bc98  mov     r11, rsp
0x18000bc9b  sub     rsp, 58h
0x18000bc9f  mov     qword ptr [r11-18h], 0
0x18000bca7  lea     rax, [r11+28h]
0x18000bcab  mov     qword ptr [r11-20h], 4
0x18000bcb3  mov     [r11-28h], rax
0x18000bcb7  lea     rax, asc_180016AC4; " "
0x18000bcbe  movzx   r9d, dx; MessageNumber
0x18000bcc2  mov     edx, 2Bh ; '+'; MessageFlags
0x18000bcc7  mov     qword ptr [r11-30h], 2
0x18000bccf  mov     [r11-38h], rax
0x18000bcd3  call    cs:__imp_TraceMessage
0x18000bcd9  add     rsp, 58h
0x18000bcdd  retn
```
