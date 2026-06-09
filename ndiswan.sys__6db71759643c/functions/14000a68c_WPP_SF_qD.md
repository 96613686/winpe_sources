# WPP_SF_qD

- ea: `0x14000a68c`
- end: `0x14000a6da`
- name: `WPP_SF_qD`
- size: `78`
- prototype: ``
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x140001be0`
- `0x140003c30`
- `0x140004be0`
- `0x1400060f0`
- `0x140006430`
- `0x140006860`
- `0x140006a50`
- `0x140024fe0`
- `0x140025070`
- `0x1400253b0`
- `0x140025440`
- `0x140026c80`
- `0x140027a50`
- `0x14002a0f0`
- `0x140030144`

## callees

- `0x140016230`

## pseudocode

```c
__int64 WPP_SF_qD(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
{
  __int64 v4; // [rsp+78h] [rbp+20h] BYREF
  va_list va; // [rsp+78h] [rbp+20h]
  va_list va1; // [rsp+80h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v4 = va_arg(va1, _QWORD);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
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
0x14000a68c  mov     r11, rsp
0x14000a68f  mov     [r11+20h], r9
0x14000a693  sub     rsp, 58h
0x14000a697  mov     rax, cs:pfnWppTraceMessage
0x14000a69e  lea     r9, [r11+28h]
0x14000a6a2  mov     qword ptr [r11-18h], 0
0x14000a6aa  mov     qword ptr [r11-20h], 4
0x14000a6b2  mov     [r11-28h], r9
0x14000a6b6  lea     r9, [r11+20h]
0x14000a6ba  mov     qword ptr [r11-30h], 8
0x14000a6c2  mov     [r11-38h], r9
0x14000a6c6  movzx   r9d, dx
0x14000a6ca  mov     edx, 2Bh ; '+'
0x14000a6cf  call    _guard_dispatch_icall
0x14000a6d4  add     rsp, 58h
0x14000a6d8  retn
```
