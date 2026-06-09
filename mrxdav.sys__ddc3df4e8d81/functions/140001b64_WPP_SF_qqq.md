# WPP_SF_qqq

- ea: `0x140001b64`
- end: `0x140001bbb`
- name: `WPP_SF_qqq`
- size: `87`
- prototype: `__int64(__int64, unsigned __int16, __int64, ...)`
- caller_count: `58`
- callee_count: `1`
- tags: ``

## callers

- `0x140003b10`
- `0x140003c20`
- `0x140003dd0`
- `0x140004dac`
- `0x140004e98`
- `0x140004f50`
- `0x140005030`
- `0x14000610c`
- `0x140010620`
- `0x1400115f0`
- `0x1400116f8`
- `0x140011a20`
- `0x140011eec`
- `0x1400128a0`
- `0x1400130e0`
- `0x1400145d0`
- `0x140014e00`
- `0x140015900`
- `0x140015c30`
- `0x1400191b0`
- `0x1400194f0`
- `0x1400195b0`
- `0x140019890`
- `0x1400199a0`
- `0x14001a480`
- `0x14001a6f0`
- `0x14001aa30`
- `0x14001ac20`
- `0x14001ae20`
- `0x14001b250`
- `0x14001b360`
- `0x14001bc30`
- `0x14001bdf0`
- `0x14001c3a0`
- `0x14001d020`
- `0x14001dec0`
- `0x14001e6a0`
- `0x14001fa70`
- `0x140020090`
- `0x140020660`
- `0x140020e80`
- `0x1400214d0`
- `0x140021720`
- `0x140021a50`
- `0x140022860`
- `0x140022970`
- `0x1400233a0`
- `0x140023bb0`
- `0x140023cc0`
- `0x140023e20`

## callees

- `0x140006880`

## pseudocode

```c
__int64 WPP_SF_qqq(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
{
  __int64 v4; // [rsp+88h] [rbp+20h] BYREF
  va_list va; // [rsp+88h] [rbp+20h]
  __int64 v6; // [rsp+90h] [rbp+28h] BYREF
  va_list va1; // [rsp+90h] [rbp+28h]
  va_list va2; // [rsp+98h] [rbp+30h] BYREF

  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v4 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v6 = va_arg(va2, _QWORD);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           (__int64 *)va,
           8,
           (__int64 *)va1,
           8,
           va2,
           8,
           0);
}

```

## disassembly

```asm
0x140001b64  mov     r11, rsp
0x140001b67  mov     [r11+20h], r9
0x140001b6b  sub     rsp, 68h
0x140001b6f  mov     rax, cs:pfnWppTraceMessage
0x140001b76  lea     r9, [r11+30h]
0x140001b7a  mov     qword ptr [r11-18h], 0
0x140001b82  mov     r10d, 8
0x140001b88  mov     [r11-20h], r10
0x140001b8c  mov     [r11-28h], r9
0x140001b90  lea     r9, [r11+28h]
0x140001b94  mov     [r11-30h], r10
0x140001b98  mov     [r11-38h], r9
0x140001b9c  lea     r9, [r11+20h]
0x140001ba0  mov     [r11-40h], r10
0x140001ba4  mov     [r11-48h], r9
0x140001ba8  movzx   r9d, dx
0x140001bac  lea     edx, [r10+23h]
0x140001bb0  call    _guard_dispatch_icall
0x140001bb5  add     rsp, 68h
0x140001bb9  retn
```
