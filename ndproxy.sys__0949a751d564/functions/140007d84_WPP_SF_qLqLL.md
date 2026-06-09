# WPP_SF_qLqLL

- ea: `0x140007d84`
- end: `0x140007e04`
- name: `WPP_SF_qLqLL`
- size: `128`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000f830`
- `0x1400166e0`
- `0x1400167a0`

## callees

- `0x140008000`

## pseudocode

```c
__int64 WPP_SF_qLqLL(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
{
  __int64 v4; // [rsp+A8h] [rbp+20h] BYREF
  va_list va; // [rsp+A8h] [rbp+20h]
  __int64 v6; // [rsp+B0h] [rbp+28h] BYREF
  va_list va1; // [rsp+B0h] [rbp+28h]
  __int64 v8; // [rsp+B8h] [rbp+30h] BYREF
  va_list va2; // [rsp+B8h] [rbp+30h]
  __int64 v10; // [rsp+C0h] [rbp+38h] BYREF
  va_list va3; // [rsp+C0h] [rbp+38h]
  va_list va4; // [rsp+C8h] [rbp+40h] BYREF

  va_start(va4, a3);
  va_start(va3, a3);
  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v4 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v6 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v8 = va_arg(va3, _QWORD);
  va_copy(va4, va3);
  v10 = va_arg(va4, _QWORD);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64 *, _QWORD, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           WPP_a6cada0c64e03ec47d691a112a859896_Traceguids,
           a2,
           (__int64 *)va,
           8,
           (__int64 *)va1,
           4,
           (__int64 *)va2,
           8,
           (__int64 *)va3,
           4,
           va4,
           4,
           0);
}

```

## disassembly

```asm
0x140007d84  mov     r11, rsp
0x140007d87  mov     [r11+20h], r9
0x140007d8b  sub     rsp, 88h
0x140007d92  mov     rax, cs:pfnWppTraceMessage
0x140007d99  lea     r8, [r11+40h]
0x140007d9d  mov     qword ptr [r11-18h], 0
0x140007da5  mov     r10d, 4
0x140007dab  mov     [r11-20h], r10
0x140007daf  mov     [r11-28h], r8
0x140007db3  lea     r8, [r11+38h]
0x140007db7  mov     [r11-30h], r10
0x140007dbb  mov     [r11-38h], r8
0x140007dbf  lea     r9d, [r10+4]
0x140007dc3  mov     [r11-40h], r9
0x140007dc7  lea     r8, [r11+30h]
0x140007dcb  mov     [r11-48h], r8
0x140007dcf  lea     r8, [r11+28h]
0x140007dd3  mov     [r11-50h], r10
0x140007dd7  mov     [r11-58h], r8
0x140007ddb  lea     r8, [r11+20h]
0x140007ddf  mov     [r11-60h], r9
0x140007de3  mov     [r11-68h], r8
0x140007de7  lea     r8, WPP_a6cada0c64e03ec47d691a112a859896_Traceguids
0x140007dee  movzx   r9d, dx
0x140007df2  lea     edx, [r10+27h]
0x140007df6  call    _guard_dispatch_icall
0x140007dfb  add     rsp, 88h
0x140007e02  retn
```
