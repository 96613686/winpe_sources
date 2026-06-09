# WPP_SF__guid_L

- ea: `0x140005398`
- end: `0x1400053e5`
- name: `WPP_SF__guid_L`
- size: `77`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400155b0`
- `0x1400168d0`

## callees

- `0x140005ef0`

## pseudocode

```c
__int64 WPP_SF__guid_L(__int64 a1, unsigned __int16 a2, __int64 a3, __int64 a4, ...)
{
  va_list va; // [rsp+80h] [rbp+28h] BYREF

  va_start(va, a4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64 *, _QWORD, __int64, __int64, __int64 *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids,
           a2,
           a4,
           16,
           (__int64 *)va,
           4,
           0);
}

```

## disassembly

```asm
0x140005398  mov     r11, rsp
0x14000539b  sub     rsp, 58h
0x14000539f  mov     rax, cs:pfnWppTraceMessage
0x1400053a6  lea     r8, [r11+28h]
0x1400053aa  mov     qword ptr [r11-18h], 0
0x1400053b2  mov     qword ptr [r11-20h], 4
0x1400053ba  mov     [r11-28h], r8
0x1400053be  lea     r8, WPP_e006ad75976b31bcff41960cb142c0e0_Traceguids
0x1400053c5  mov     qword ptr [r11-30h], 10h
0x1400053cd  mov     [r11-38h], r9
0x1400053d1  movzx   r9d, dx
0x1400053d5  mov     edx, 2Bh ; '+'
0x1400053da  call    _guard_dispatch_icall
0x1400053df  add     rsp, 58h
0x1400053e3  retn
```
