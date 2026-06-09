# WPP_SF_DDDDDDDDDDDDDDDD

- ea: `0x1400030c4`
- end: `0x1400031e4`
- name: `WPP_SF_DDDDDDDDDDDDDDDD`
- size: `288`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400024e0`
- `0x140011518`
- `0x140016440`

## callees

- `0x140004830`

## pseudocode

```c
__int64 WPP_SF_DDDDDDDDDDDDDDDD(__int64 a1, unsigned __int16 a2, __int64 a3, int a4, ...)
{
  int v5; // [rsp+160h] [rbp-58h] BYREF
  __int64 v6; // [rsp+168h] [rbp-50h] BYREF
  va_list va; // [rsp+168h] [rbp-50h]
  __int64 v8; // [rsp+170h] [rbp-48h] BYREF
  va_list va1; // [rsp+170h] [rbp-48h]
  __int64 v10; // [rsp+178h] [rbp-40h] BYREF
  va_list va2; // [rsp+178h] [rbp-40h]
  __int64 v12; // [rsp+180h] [rbp-38h] BYREF
  va_list va3; // [rsp+180h] [rbp-38h]
  __int64 v14; // [rsp+188h] [rbp-30h] BYREF
  va_list va4; // [rsp+188h] [rbp-30h]
  __int64 v16; // [rsp+190h] [rbp-28h] BYREF
  va_list va5; // [rsp+190h] [rbp-28h]
  __int64 v18; // [rsp+198h] [rbp-20h] BYREF
  va_list va6; // [rsp+198h] [rbp-20h]
  __int64 v20; // [rsp+1A0h] [rbp-18h] BYREF
  va_list va7; // [rsp+1A0h] [rbp-18h]
  __int64 v22; // [rsp+1A8h] [rbp-10h] BYREF
  va_list va8; // [rsp+1A8h] [rbp-10h]
  __int64 v24; // [rsp+1B0h] [rbp-8h] BYREF
  va_list va9; // [rsp+1B0h] [rbp-8h]
  __int64 v26; // [rsp+1B8h] [rbp+0h] BYREF
  va_list va10; // [rsp+1B8h] [rbp+0h]
  __int64 v28; // [rsp+1C0h] [rbp+8h] BYREF
  va_list va11; // [rsp+1C0h] [rbp+8h]
  __int64 v30; // [rsp+1C8h] [rbp+10h] BYREF
  va_list va12; // [rsp+1C8h] [rbp+10h]
  __int64 v32; // [rsp+1D0h] [rbp+18h] BYREF
  va_list va13; // [rsp+1D0h] [rbp+18h]
  va_list va14; // [rsp+1D8h] [rbp+20h] BYREF

  va_start(va14, a4);
  va_start(va13, a4);
  va_start(va12, a4);
  va_start(va11, a4);
  va_start(va10, a4);
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
  va_copy(va10, va9);
  v24 = va_arg(va10, _QWORD);
  va_copy(va11, va10);
  v26 = va_arg(va11, _QWORD);
  va_copy(va12, va11);
  v28 = va_arg(va12, _QWORD);
  va_copy(va13, va12);
  v30 = va_arg(va13, _QWORD);
  va_copy(va14, va13);
  v32 = va_arg(va14, _QWORD);
  v5 = a4;
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, int *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
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
           (__int64 *)va9,
           4,
           (__int64 *)va10,
           4,
           (__int64 *)va11,
           4,
           (__int64 *)va12,
           4,
           (__int64 *)va13,
           4,
           va14,
           4,
           0);
}

```

## disassembly

```asm
0x1400030c4  mov     r11, rsp
0x1400030c7  mov     [r11+20h], r9d
0x1400030cb  push    rbp
0x1400030cc  lea     rbp, [r11+78h]
0x1400030d0  sub     rsp, 130h
0x1400030d7  mov     qword ptr [r11-18h], 0
0x1400030df  lea     r9, [rbp-80h+arg_90]
0x1400030e3  mov     rax, cs:pfnWppTraceMessage
0x1400030ea  mov     r10d, 4
0x1400030f0  mov     [r11-20h], r10
0x1400030f4  mov     [r11-28h], r9
0x1400030f8  lea     r9, [rbp-80h+arg_88]
0x1400030fc  mov     [r11-30h], r10
0x140003100  mov     [r11-38h], r9
0x140003104  lea     r9, [rbp-80h+arg_80]
0x140003108  mov     [r11-40h], r10
0x14000310c  mov     [r11-48h], r9
0x140003110  lea     r9, [rbp-80h+arg_78]
0x140003114  mov     [r11-50h], r10
0x140003118  mov     [r11-58h], r9
0x14000311c  lea     r9, [rbp-80h+arg_70]
0x140003120  mov     [r11-60h], r10
0x140003124  mov     [r11-68h], r9
0x140003128  lea     r9, [rbp-80h+arg_68]
0x14000312c  mov     [r11-70h], r10
0x140003130  mov     [r11-78h], r9
0x140003134  lea     r9, [rbp-80h+arg_60]
0x140003138  mov     [r11-80h], r10
0x14000313c  mov     [r11-88h], r9
0x140003143  lea     r9, [rbp-80h+arg_58]
0x140003147  mov     [r11-90h], r10
0x14000314e  mov     [r11-98h], r9
0x140003155  lea     r9, [rbp-80h+arg_50]
0x140003159  mov     [r11-0A0h], r10
0x140003160  mov     [r11-0A8h], r9
0x140003167  lea     r9, [rbp-80h+arg_48]
0x14000316b  mov     [r11-0B0h], r10
0x140003172  mov     [r11-0B8h], r9
0x140003179  lea     r9, [rbp-80h+arg_40]
0x14000317d  mov     [rsp+78h], r10
0x140003182  mov     [rsp+130h+var_C0], r9
0x140003187  lea     r9, [rbp-80h+arg_38]
0x14000318b  mov     [rsp+130h+var_C8], r10
0x140003190  mov     [rsp+130h+var_D0], r9
0x140003195  lea     r9, [rbp-80h+arg_30]
0x140003199  mov     [rsp+130h+var_D8], r10
0x14000319e  mov     [rsp+130h+var_E0], r9
0x1400031a3  lea     r9, [rbp-80h+arg_28]
0x1400031a7  mov     [rsp+130h+var_E8], r10
0x1400031ac  mov     [rsp+130h+var_F0], r9
0x1400031b1  lea     r9, [rbp-80h+arg_20]
0x1400031b5  mov     [rsp+130h+var_F8], r10
0x1400031ba  mov     [rsp+130h+var_100], r9
0x1400031bf  lea     r9, [rbp-80h+arg_18]
0x1400031c3  mov     [rsp+130h+var_108], r10
0x1400031c8  mov     [rsp+130h+var_110], r9
0x1400031cd  movzx   r9d, dx
0x1400031d1  lea     edx, [r10+27h]
0x1400031d5  call    _guard_dispatch_icall
0x1400031da  add     rsp, 130h
0x1400031e1  pop     rbp
0x1400031e2  retn
```
