# WPP_SF_qqL

- ea: `0x18000e044`
- end: `0x18000e0a7`
- name: `WPP_SF_qqL`
- size: `99`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180005160`
- `0x18000c93c`
- `0x18000cbb4`
- `0x18000d01c`
- `0x18000d664`
- `0x18000dad4`

## callees

- `0x180010980`

## pseudocode

```c
__int64 WPP_SF_qqL(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
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
  return ((__int64 (__fastcall *)(__int64, __int64, void *, _QWORD, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           &WPP_aba6cc221655371604011c64d2fbf4cc_Traceguids,
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
0x18000e044  mov     r11, rsp
0x18000e047  mov     [r11+20h], r9
0x18000e04b  sub     rsp, 68h
0x18000e04f  mov     rax, cs:pfnWppTraceMessage
0x18000e056  lea     r8, [r11+30h]
0x18000e05a  mov     qword ptr [r11-18h], 0
0x18000e062  mov     r9d, 8
0x18000e068  mov     qword ptr [r11-20h], 4
0x18000e070  mov     [r11-28h], r8
0x18000e074  lea     r8, [r11+28h]
0x18000e078  mov     [r11-30h], r9
0x18000e07c  mov     [r11-38h], r8
0x18000e080  lea     r8, [r11+20h]
0x18000e084  mov     [r11-40h], r9
0x18000e088  mov     [r11-48h], r8
0x18000e08c  lea     r8, WPP_aba6cc221655371604011c64d2fbf4cc_Traceguids
0x18000e093  movzx   r9d, dx
0x18000e097  mov     edx, 2Bh ; '+'
0x18000e09c  call    _guard_dispatch_icall
0x18000e0a1  add     rsp, 68h
0x18000e0a5  retn
```
