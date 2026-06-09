# WPP_SF_q

- ea: `0x18000ded4`
- end: `0x18000df12`
- name: `WPP_SF_q`
- size: `62`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180005718`
- `0x18000cbb4`
- `0x18000f900`
- `0x18000fd60`

## callees

- `0x180010980`

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
0x18000ded4  mov     r11, rsp
0x18000ded7  mov     [r11+20h], r9
0x18000dedb  sub     rsp, 48h
0x18000dedf  mov     rax, cs:pfnWppTraceMessage
0x18000dee6  lea     r9, [r11+20h]
0x18000deea  mov     qword ptr [r11-18h], 0
0x18000def2  mov     qword ptr [r11-20h], 8
0x18000defa  mov     [r11-28h], r9
0x18000defe  movzx   r9d, dx
0x18000df02  mov     edx, 2Bh ; '+'
0x18000df07  call    _guard_dispatch_icall
0x18000df0c  add     rsp, 48h
0x18000df10  retn
```
