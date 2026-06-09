# WPP_SF_Dq

- ea: `0x14000b5d8`
- end: `0x14000b626`
- name: `WPP_SF_Dq`
- size: `78`
- prototype: ``
- caller_count: `28`
- callee_count: `1`
- tags: ``

## callers

- `0x140003f74`
- `0x1400041ac`
- `0x140004314`
- `0x1400047fc`
- `0x140004cb4`
- `0x1400057f4`
- `0x140005e1c`
- `0x1400060c0`
- `0x1400061fc`
- `0x140006334`
- `0x14000648c`
- `0x1400065d0`
- `0x140006808`
- `0x140006d50`
- `0x140006fd8`
- `0x1400078f4`
- `0x140007cb8`
- `0x14000881c`
- `0x140009070`
- `0x140009110`
- `0x1400091b8`
- `0x140009258`
- `0x1400092f8`
- `0x1400093a0`
- `0x1400094a0`
- `0x140009540`
- `0x1400096b0`
- `0x14001a220`

## callees

- `0x140024bf0`

## pseudocode

```c
__int64 WPP_SF_Dq(__int64 a1, unsigned __int16 a2, __int64 a3, int a4, ...)
{
  int v5; // [rsp+78h] [rbp+20h] BYREF
  va_list va; // [rsp+80h] [rbp+28h] BYREF

  va_start(va, a4);
  v5 = a4;
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, int *, __int64, __int64 *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           &v5,
           4,
           (__int64 *)va,
           8,
           0);
}

```

## disassembly

```asm
0x14000b5d8  mov     r11, rsp
0x14000b5db  mov     [r11+20h], r9d
0x14000b5df  sub     rsp, 58h
0x14000b5e3  mov     rax, cs:pfnWppTraceMessage
0x14000b5ea  lea     r9, [r11+28h]
0x14000b5ee  mov     qword ptr [r11-18h], 0
0x14000b5f6  mov     qword ptr [r11-20h], 8
0x14000b5fe  mov     [r11-28h], r9
0x14000b602  lea     r9, [r11+20h]
0x14000b606  mov     qword ptr [r11-30h], 4
0x14000b60e  mov     [r11-38h], r9
0x14000b612  movzx   r9d, dx
0x14000b616  mov     edx, 2Bh ; '+'
0x14000b61b  call    _guard_dispatch_icall
0x14000b620  add     rsp, 58h
0x14000b624  retn
```
