# WPP_SF_qqD

- ea: `0x1400029b0`
- end: `0x140002a0b`
- name: `WPP_SF_qqD`
- size: `91`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140001070`
- `0x14001a370`
- `0x14001a760`
- `0x14001b860`
- `0x14001c300`
- `0x14001cff0`

## callees

- `0x1400054e0`

## pseudocode

```c
__int64 WPP_SF_qqD(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
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
           4,
           0);
}

```

## disassembly

```asm
0x1400029b0  mov     r11, rsp
0x1400029b3  mov     [r11+20h], r9
0x1400029b7  sub     rsp, 68h
0x1400029bb  mov     rax, cs:pfnWppTraceMessage
0x1400029c2  lea     r9, [r11+30h]
0x1400029c6  mov     qword ptr [r11-18h], 0
0x1400029ce  mov     r10d, 8
0x1400029d4  mov     qword ptr [r11-20h], 4
0x1400029dc  mov     [r11-28h], r9
0x1400029e0  lea     r9, [r11+28h]
0x1400029e4  mov     [r11-30h], r10
0x1400029e8  mov     [r11-38h], r9
0x1400029ec  lea     r9, [r11+20h]
0x1400029f0  mov     [r11-40h], r10
0x1400029f4  mov     [r11-48h], r9
0x1400029f8  movzx   r9d, dx
0x1400029fc  lea     edx, [r10+23h]
0x140002a00  call    _guard_dispatch_icall
0x140002a05  add     rsp, 68h
0x140002a09  retn
```
