# WPP_SF__guid_D

- ea: `0x140002fc4`
- end: `0x14000300a`
- name: `WPP_SF__guid_D`
- size: `70`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x140001010`
- `0x140010c58`
- `0x140011500`
- `0x140012290`
- `0x140013150`
- `0x1400133f0`
- `0x140013dc0`
- `0x140013eb0`
- `0x1400144c4`
- `0x1400155b0`

## callees

- `0x140005ef0`

## pseudocode

```c
__int64 WPP_SF__guid_D(__int64 a1, unsigned __int16 a2, __int64 a3, __int64 a4, ...)
{
  va_list va; // [rsp+80h] [rbp+28h] BYREF

  va_start(va, a4);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, __int64, __int64, __int64 *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
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
0x140002fc4  mov     r11, rsp
0x140002fc7  sub     rsp, 58h
0x140002fcb  mov     rax, cs:pfnWppTraceMessage
0x140002fd2  lea     r10, [r11+28h]
0x140002fd6  mov     qword ptr [r11-18h], 0
0x140002fde  mov     qword ptr [r11-20h], 4
0x140002fe6  mov     [r11-28h], r10
0x140002fea  mov     qword ptr [r11-30h], 10h
0x140002ff2  mov     [r11-38h], r9
0x140002ff6  movzx   r9d, dx
0x140002ffa  mov     edx, 2Bh ; '+'
0x140002fff  call    _guard_dispatch_icall
0x140003004  add     rsp, 58h
0x140003008  retn
```
