# WPP_SF_sd

- ea: `0x1800071ac`
- end: `0x1800071f2`
- name: `WPP_SF_sd`
- size: `70`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `19`
- callee_count: `0`
- tags: ``

## callers

- `0x1800079fc`
- `0x180007fb4`
- `0x1800081b8`
- `0x1800086c8`
- `0x180008b90`
- `0x180008d7c`
- `0x1800093cc`
- `0x180009af8`
- `0x18000a19c`
- `0x18000a334`
- `0x18000a4a0`
- `0x18000b210`
- `0x18000c2b0`
- `0x18000c340`
- `0x18000e46a`
- `0x18000e4e8`
- `0x18000e5f4`
- `0x18000e971`
- `0x18000ebba`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x1800071e7`
- `ADVAPI32!TraceMessage` at `0x1800071e7`

## pseudocode

```c
ULONG WPP_SF_sd(TRACEHANDLE a1, USHORT a2, const GUID *a3, __int64 a4, ...)
{
  va_list va; // [rsp+80h] [rbp+28h] BYREF

  va_start(va, a4);
  return TraceMessage(a1, 0x2Bu, a3, a2, "NPSDS", 6, va, 4, 0);
}

```

## disassembly

```asm
0x1800071ac  mov     r11, rsp
0x1800071af  sub     rsp, 58h
0x1800071b3  mov     qword ptr [r11-18h], 0
0x1800071bb  lea     rax, [r11+28h]
0x1800071bf  mov     qword ptr [r11-20h], 4
0x1800071c7  mov     [r11-28h], rax
0x1800071cb  lea     rax, aNpsds; "NPSDS"
0x1800071d2  movzx   r9d, dx; MessageNumber
0x1800071d6  mov     edx, 2Bh ; '+'; MessageFlags
0x1800071db  mov     qword ptr [r11-30h], 6
0x1800071e3  mov     [r11-38h], rax
0x1800071e7  call    cs:__imp_TraceMessage
0x1800071ed  add     rsp, 58h
0x1800071f1  retn
```
