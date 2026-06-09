# WPP_SF_qL

- ea: `0x18000df18`
- end: `0x18000df6d`
- name: `WPP_SF_qL`
- size: `85`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x1800021bc`
- `0x180004e7c`
- `0x18000cbb4`
- `0x18000d2f0`
- `0x18000d574`
- `0x18000d664`
- `0x18000d86c`
- `0x18000d94c`

## callees

- `0x180010980`

## pseudocode

```c
__int64 WPP_SF_qL(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
{
  __int64 v4; // [rsp+78h] [rbp+20h] BYREF
  va_list va; // [rsp+78h] [rbp+20h]
  va_list va1; // [rsp+80h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v4 = va_arg(va1, _QWORD);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64 *, _QWORD, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           WPP_aba6cc221655371604011c64d2fbf4cc_Traceguids,
           a2,
           (__int64 *)va,
           8,
           va1,
           4,
           0);
}

```

## disassembly

```asm
0x18000df18  mov     r11, rsp
0x18000df1b  mov     [r11+20h], r9
0x18000df1f  sub     rsp, 58h
0x18000df23  mov     rax, cs:pfnWppTraceMessage
0x18000df2a  lea     r8, [r11+28h]
0x18000df2e  mov     qword ptr [r11-18h], 0
0x18000df36  mov     qword ptr [r11-20h], 4
0x18000df3e  mov     [r11-28h], r8
0x18000df42  lea     r8, [r11+20h]
0x18000df46  mov     qword ptr [r11-30h], 8
0x18000df4e  mov     [r11-38h], r8
0x18000df52  lea     r8, WPP_aba6cc221655371604011c64d2fbf4cc_Traceguids
0x18000df59  movzx   r9d, dx
0x18000df5d  mov     edx, 2Bh ; '+'
0x18000df62  call    _guard_dispatch_icall
0x18000df67  add     rsp, 58h
0x18000df6b  retn
```
