# WPP_SF_qdd

- ea: `0x14000429c`
- end: `0x1400042ff`
- name: `WPP_SF_qdd`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000f8d8`
- `0x140017650`
- `0x140018190`

## callees

- `0x140007710`

## pseudocode

```c
__int64 WPP_SF_qdd(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
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
  return ((__int64 (__fastcall *)(__int64, __int64, __int64 *, _QWORD, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids,
           a2,
           (__int64 *)va,
           8,
           (__int64 *)va1,
           4,
           va2,
           4,
           0);
}

```

## disassembly

```asm
0x14000429c  mov     r11, rsp
0x14000429f  mov     [r11+20h], r9
0x1400042a3  sub     rsp, 68h
0x1400042a7  mov     rax, cs:pfnWppTraceMessage
0x1400042ae  lea     r8, [r11+30h]
0x1400042b2  mov     qword ptr [r11-18h], 0
0x1400042ba  mov     r9d, 4
0x1400042c0  mov     [r11-20h], r9
0x1400042c4  mov     [r11-28h], r8
0x1400042c8  lea     r8, [r11+28h]
0x1400042cc  mov     [r11-30h], r9
0x1400042d0  mov     [r11-38h], r8
0x1400042d4  lea     r8, [r11+20h]
0x1400042d8  mov     qword ptr [r11-40h], 8
0x1400042e0  mov     [r11-48h], r8
0x1400042e4  lea     r8, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids
0x1400042eb  movzx   r9d, dx
0x1400042ef  mov     edx, 2Bh ; '+'
0x1400042f4  call    _guard_dispatch_icall
0x1400042f9  add     rsp, 68h
0x1400042fd  retn
```
