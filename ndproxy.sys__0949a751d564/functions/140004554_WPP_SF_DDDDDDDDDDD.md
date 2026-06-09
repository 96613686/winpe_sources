# WPP_SF_DDDDDDDDDDD

- ea: `0x140004554`
- end: `0x140004620`
- name: `WPP_SF_DDDDDDDDDDD`
- size: `204`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140002670`
- `0x1400062c0`

## callees

- `0x140008000`

## pseudocode

```c
__int64 WPP_SF_DDDDDDDDDDD(__int64 a1, unsigned __int16 a2, __int64 a3, int a4, ...)
{
  int v5; // [rsp+110h] [rbp+2Fh] BYREF
  __int64 v6; // [rsp+118h] [rbp+37h] BYREF
  va_list va; // [rsp+118h] [rbp+37h]
  __int64 v8; // [rsp+120h] [rbp+3Fh] BYREF
  va_list va1; // [rsp+120h] [rbp+3Fh]
  __int64 v10; // [rsp+128h] [rbp+47h] BYREF
  va_list va2; // [rsp+128h] [rbp+47h]
  __int64 v12; // [rsp+130h] [rbp+4Fh] BYREF
  va_list va3; // [rsp+130h] [rbp+4Fh]
  __int64 v14; // [rsp+138h] [rbp+57h] BYREF
  va_list va4; // [rsp+138h] [rbp+57h]
  __int64 v16; // [rsp+140h] [rbp+5Fh] BYREF
  va_list va5; // [rsp+140h] [rbp+5Fh]
  __int64 v18; // [rsp+148h] [rbp+67h] BYREF
  va_list va6; // [rsp+148h] [rbp+67h]
  __int64 v20; // [rsp+150h] [rbp+6Fh] BYREF
  va_list va7; // [rsp+150h] [rbp+6Fh]
  __int64 v22; // [rsp+158h] [rbp+77h] BYREF
  va_list va8; // [rsp+158h] [rbp+77h]
  va_list va9; // [rsp+160h] [rbp+7Fh] BYREF

  va_start(va9, a4);
  va_start(va8, a4);
  va_start(va7, a4);
  va_start(va6, a4);
  va_start(va5, a4);
  va_start(va4, a4);
  va_start(va3, a4);
  va_start(va2, a4);
  va_start(va1, a4);
  va_start(va, a4);
  v6 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v8 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v10 = va_arg(va3, _QWORD);
  va_copy(va4, va3);
  v12 = va_arg(va4, _QWORD);
  va_copy(va5, va4);
  v14 = va_arg(va5, _QWORD);
  va_copy(va6, va5);
  v16 = va_arg(va6, _QWORD);
  va_copy(va7, va6);
  v18 = va_arg(va7, _QWORD);
  va_copy(va8, va7);
  v20 = va_arg(va8, _QWORD);
  va_copy(va9, va8);
  v22 = va_arg(va9, _QWORD);
  v5 = a4;
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, int *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           &v5,
           4,
           (__int64 *)va,
           4,
           (__int64 *)va1,
           4,
           (__int64 *)va2,
           4,
           (__int64 *)va3,
           4,
           (__int64 *)va4,
           4,
           (__int64 *)va5,
           4,
           (__int64 *)va6,
           4,
           (__int64 *)va7,
           4,
           (__int64 *)va8,
           4,
           va9,
           4,
           0);
}

```

## disassembly

```asm
0x140004554  mov     r11, rsp
0x140004557  mov     [r11+20h], r9d
0x14000455b  push    rbp
0x14000455c  lea     rbp, [r11-0Fh]
0x140004560  sub     rsp, 0E0h
0x140004567  mov     rax, cs:pfnWppTraceMessage
0x14000456e  lea     r9, [rbp+7+arg_68]
0x140004572  mov     qword ptr [r11-18h], 0
0x14000457a  mov     r10d, 4
0x140004580  mov     [r11-20h], r10
0x140004584  mov     [r11-28h], r9
0x140004588  lea     r9, [rbp+7+arg_60]
0x14000458c  mov     [r11-30h], r10
0x140004590  mov     [r11-38h], r9
0x140004594  lea     r9, [rbp+7+arg_58]
0x140004598  mov     [r11-40h], r10
0x14000459c  mov     [r11-48h], r9
0x1400045a0  lea     r9, [rbp+7+arg_50]
0x1400045a4  mov     [r11-50h], r10
0x1400045a8  mov     [r11-58h], r9
0x1400045ac  lea     r9, [rbp+7+arg_48]
0x1400045b0  mov     [r11-60h], r10
0x1400045b4  mov     [r11-68h], r9
0x1400045b8  lea     r9, [rbp+7+arg_40]
0x1400045bc  mov     [r11-70h], r10
0x1400045c0  mov     [r11-78h], r9
0x1400045c4  lea     r9, [rbp+7+arg_38]
0x1400045c8  mov     [r11-80h], r10
0x1400045cc  mov     [rsp+60h], r9
0x1400045d1  lea     r9, [rbp+7+arg_30]
0x1400045d5  mov     [rsp+0E0h+var_88], r10
0x1400045da  mov     [rsp+0E0h+var_90], r9
0x1400045df  lea     r9, [rbp+7+arg_28]
0x1400045e3  mov     [rsp+0E0h+var_98], r10
0x1400045e8  mov     [rsp+0E0h+var_A0], r9
0x1400045ed  lea     r9, [rbp+7+arg_20]
0x1400045f1  mov     [rsp+0E0h+var_A8], r10
0x1400045f6  mov     [rsp+0E0h+var_B0], r9
0x1400045fb  lea     r9, [rbp+7+arg_18]
0x1400045ff  mov     [rsp+0E0h+var_B8], r10
0x140004604  mov     [rsp+0E0h+var_C0], r9
0x140004609  movzx   r9d, dx
0x14000460d  lea     edx, [r10+27h]
0x140004611  call    _guard_dispatch_icall
0x140004616  add     rsp, 0E0h
0x14000461d  pop     rbp
0x14000461e  retn
```
