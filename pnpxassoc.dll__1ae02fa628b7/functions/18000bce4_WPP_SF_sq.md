# WPP_SF_sq

- ea: `0x18000bce4`
- end: `0x18000bd2a`
- name: `WPP_SF_sq`
- size: `70`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `45`
- callee_count: `0`
- tags: ``

## callers

- `0x1800098c8`
- `0x180009990`
- `0x180009b20`
- `0x180009c10`
- `0x18000a070`
- `0x18000a28c`
- `0x18000a480`
- `0x18000a780`
- `0x18000a854`
- `0x18000a9e8`
- `0x18000b2e4`
- `0x18000b500`
- `0x18000b5c0`
- `0x18000b8e0`
- `0x18000b9b4`
- `0x18000bd8c`
- `0x18000bfcc`
- `0x18000c144`
- `0x18000c33c`
- `0x18000c490`
- `0x18000c510`
- `0x18000c5a0`
- `0x18000cbf8`
- `0x18000ccec`
- `0x18000d09c`
- `0x18000d16c`
- `0x18000d500`
- `0x18000d5b0`
- `0x18000d6a0`
- `0x18000d7d8`
- `0x18000d880`
- `0x18000d9d0`
- `0x18000db10`
- `0x18000dbc0`
- `0x18000de14`
- `0x18000ded0`
- `0x18000e104`
- `0x18000e340`
- `0x18000e540`
- `0x18000e6e0`
- `0x18000e870`
- `0x18000e9d0`
- `0x18000ebc8`
- `0x18000ed14`
- `0x18000f020`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x18000bd1f`
- `ADVAPI32!TraceMessage` at `0x18000bd1f`

## pseudocode

```c
ULONG WPP_SF_sq(TRACEHANDLE a1, USHORT a2, const GUID *a3, __int64 a4, ...)
{
  va_list va; // [rsp+80h] [rbp+28h] BYREF

  va_start(va, a4);
  return TraceMessage(a1, 0x2Bu, a3, a2, " ", 2, va, 8, 0);
}

```

## disassembly

```asm
0x18000bce4  mov     r11, rsp
0x18000bce7  sub     rsp, 58h
0x18000bceb  mov     qword ptr [r11-18h], 0
0x18000bcf3  lea     rax, [r11+28h]
0x18000bcf7  mov     qword ptr [r11-20h], 8
0x18000bcff  mov     [r11-28h], rax
0x18000bd03  lea     rax, asc_180016AC4; " "
0x18000bd0a  movzx   r9d, dx; MessageNumber
0x18000bd0e  mov     edx, 2Bh ; '+'; MessageFlags
0x18000bd13  mov     qword ptr [r11-30h], 2
0x18000bd1b  mov     [r11-38h], rax
0x18000bd1f  call    cs:__imp_TraceMessage
0x18000bd25  add     rsp, 58h
0x18000bd29  retn
```
