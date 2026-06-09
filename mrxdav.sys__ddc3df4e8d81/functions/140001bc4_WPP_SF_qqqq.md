# WPP_SF_qqqq

- ea: `0x140001bc4`
- end: `0x140001c27`
- name: `WPP_SF_qqqq`
- size: `99`
- prototype: `__int64(__int64, unsigned __int16, __int64, ...)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140010620`
- `0x1400189a0`
- `0x140025e10`
- `0x140026dfc`
- `0x140027f1c`

## callees

- `0x140006880`

## pseudocode

```c
__int64 WPP_SF_qqqq(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
{
  __int64 v4; // [rsp+98h] [rbp+20h] BYREF
  va_list va; // [rsp+98h] [rbp+20h]
  __int64 v6; // [rsp+A0h] [rbp+28h] BYREF
  va_list va1; // [rsp+A0h] [rbp+28h]
  __int64 v8; // [rsp+A8h] [rbp+30h] BYREF
  va_list va2; // [rsp+A8h] [rbp+30h]
  va_list va3; // [rsp+B0h] [rbp+38h] BYREF

  va_start(va3, a3);
  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v4 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v6 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v8 = va_arg(va3, _QWORD);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           (__int64 *)va,
           8,
           (__int64 *)va1,
           8,
           (__int64 *)va2,
           8,
           va3,
           8,
           0);
}

```

## disassembly

```asm
0x140001bc4  mov     r11, rsp
0x140001bc7  mov     [r11+20h], r9
0x140001bcb  sub     rsp, 78h
0x140001bcf  mov     rax, cs:pfnWppTraceMessage
0x140001bd6  lea     r9, [r11+38h]
0x140001bda  mov     qword ptr [r11-18h], 0
0x140001be2  mov     r10d, 8
0x140001be8  mov     [r11-20h], r10
0x140001bec  mov     [r11-28h], r9
0x140001bf0  lea     r9, [r11+30h]
0x140001bf4  mov     [r11-30h], r10
0x140001bf8  mov     [r11-38h], r9
0x140001bfc  lea     r9, [r11+28h]
0x140001c00  mov     [r11-40h], r10
0x140001c04  mov     [r11-48h], r9
0x140001c08  lea     r9, [r11+20h]
0x140001c0c  mov     [r11-50h], r10
0x140001c10  mov     [r11-58h], r9
0x140001c14  movzx   r9d, dx
0x140001c18  lea     edx, [r10+23h]
0x140001c1c  call    _guard_dispatch_icall
0x140001c21  add     rsp, 78h
0x140001c25  retn
```
