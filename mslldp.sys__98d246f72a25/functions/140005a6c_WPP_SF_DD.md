# WPP_SF_DD

- ea: `0x140005a6c`
- end: `0x140005ab7`
- name: `WPP_SF_DD`
- size: `75`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x140001db0`
- `0x140002050`
- `0x1400022c0`
- `0x1400026c0`
- `0x140002794`
- `0x140002fe0`
- `0x140011390`
- `0x14001186c`
- `0x140011cac`
- `0x140012180`

## callees

- `0x140006670`

## pseudocode

```c
__int64 WPP_SF_DD(__int64 a1, unsigned __int16 a2, __int64 a3, int a4, ...)
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
           4,
           0);
}

```

## disassembly

```asm
0x140005a6c  mov     r11, rsp
0x140005a6f  mov     [r11+20h], r9d
0x140005a73  sub     rsp, 58h
0x140005a77  mov     rax, cs:pfnWppTraceMessage
0x140005a7e  lea     r9, [r11+28h]
0x140005a82  mov     qword ptr [r11-18h], 0
0x140005a8a  mov     r10d, 4
0x140005a90  mov     [r11-20h], r10
0x140005a94  mov     [r11-28h], r9
0x140005a98  lea     r9, [r11+20h]
0x140005a9c  mov     [r11-30h], r10
0x140005aa0  mov     [r11-38h], r9
0x140005aa4  movzx   r9d, dx
0x140005aa8  lea     edx, [r10+27h]
0x140005aac  call    _guard_dispatch_icall
0x140005ab1  add     rsp, 58h
0x140005ab5  retn
```
