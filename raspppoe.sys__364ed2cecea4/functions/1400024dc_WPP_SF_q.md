# WPP_SF_q

- ea: `0x1400024dc`
- end: `0x14000251a`
- name: `WPP_SF_q`
- size: `62`
- prototype: ``
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x140001608`
- `0x140002e0c`
- `0x14001052c`
- `0x140010714`
- `0x1400108d4`
- `0x140010e50`
- `0x14001169c`
- `0x1400119ec`
- `0x140011cdc`
- `0x1400152f4`
- `0x140015660`
- `0x140016534`
- `0x140017cf0`

## callees

- `0x140006b80`

## pseudocode

```c
__int64 WPP_SF_q(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
{
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, __int64 *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           (__int64 *)va,
           8,
           0);
}

```

## disassembly

```asm
0x1400024dc  mov     r11, rsp
0x1400024df  mov     [r11+20h], r9
0x1400024e3  sub     rsp, 48h
0x1400024e7  mov     rax, cs:pfnWppTraceMessage
0x1400024ee  lea     r9, [r11+20h]
0x1400024f2  mov     qword ptr [r11-18h], 0
0x1400024fa  mov     qword ptr [r11-20h], 8
0x140002502  mov     [r11-28h], r9
0x140002506  movzx   r9d, dx
0x14000250a  mov     edx, 2Bh ; '+'
0x14000250f  call    _guard_dispatch_icall
0x140002514  add     rsp, 48h
0x140002518  retn
```
