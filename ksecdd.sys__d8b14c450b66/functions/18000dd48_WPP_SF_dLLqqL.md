# WPP_SF_dLLqqL

- ea: `0x18000dd48`
- end: `0x18000ddd7`
- name: `WPP_SF_dLLqqL`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000d2f0`

## callees

- `0x180010920`

## pseudocode

```c
__int64 WPP_SF_dLLqqL(__int64 a1, __int64 a2, __int64 a3, int a4, ...)
{
  int v5; // [rsp+B8h] [rbp+20h] BYREF
  __int64 v6; // [rsp+C0h] [rbp+28h] BYREF
  va_list va; // [rsp+C0h] [rbp+28h]
  __int64 v8; // [rsp+C8h] [rbp+30h] BYREF
  va_list va1; // [rsp+C8h] [rbp+30h]
  __int64 v10; // [rsp+D0h] [rbp+38h] BYREF
  va_list va2; // [rsp+D0h] [rbp+38h]
  __int64 v12; // [rsp+D8h] [rbp+40h] BYREF
  va_list va3; // [rsp+D8h] [rbp+40h]
  va_list va4; // [rsp+E0h] [rbp+48h] BYREF

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
  v5 = a4;
  return ((__int64 (__fastcall *)(__int64, __int64, __int64 *, __int64, int *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           WPP_aba6cc221655371604011c64d2fbf4cc_Traceguids,
           21,
           &v5,
           4,
           (__int64 *)va,
           4,
           (__int64 *)va1,
           4,
           (__int64 *)va2,
           8,
           (__int64 *)va3,
           8,
           va4,
           4,
           0);
}

```

## disassembly

```asm
0x18000dd48  mov     r11, rsp
0x18000dd4b  mov     [r11+20h], r9d
0x18000dd4f  sub     rsp, 98h
0x18000dd56  mov     rax, cs:pfnWppTraceMessage
0x18000dd5d  lea     rdx, [r11+48h]
0x18000dd61  mov     qword ptr [r11-18h], 0
0x18000dd69  mov     r10d, 15h
0x18000dd6f  lea     r9d, [r10-11h]
0x18000dd73  mov     [r11-20h], r9
0x18000dd77  lea     r8d, [r10-0Dh]
0x18000dd7b  mov     [r11-28h], rdx
0x18000dd7f  lea     rdx, [r11+40h]
0x18000dd83  mov     [r11-30h], r8
0x18000dd87  mov     [r11-38h], rdx
0x18000dd8b  lea     rdx, [r11+38h]
0x18000dd8f  mov     [r11-40h], r8
0x18000dd93  lea     r8, WPP_aba6cc221655371604011c64d2fbf4cc_Traceguids
0x18000dd9a  mov     [r11-48h], rdx
0x18000dd9e  lea     rdx, [r11+30h]
0x18000dda2  mov     [r11-50h], r9
0x18000dda6  mov     [r11-58h], rdx
0x18000ddaa  lea     rdx, [r11+28h]
0x18000ddae  mov     [r11-60h], r9
0x18000ddb2  mov     [r11-68h], rdx
0x18000ddb6  lea     rdx, [r11+20h]
0x18000ddba  mov     [r11-70h], r9
0x18000ddbe  mov     r9d, r10d
0x18000ddc1  mov     [r11-78h], rdx
0x18000ddc5  lea     edx, [r10+16h]
0x18000ddc9  call    _guard_dispatch_icall
0x18000ddce  add     rsp, 98h
0x18000ddd5  retn
```
