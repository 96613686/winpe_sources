# WPP_SF_D

- ea: `0x180007bd8`
- end: `0x180007c16`
- name: `WPP_SF_D`
- size: `62`
- prototype: ``
- caller_count: `33`
- callee_count: `1`
- tags: ``

## callers

- `0x1800021bc`
- `0x180002a84`
- `0x180005160`
- `0x180006bf4`
- `0x180006d84`
- `0x180007d40`
- `0x180007e38`
- `0x18000b3c4`
- `0x18000ba40`
- `0x18000bd48`
- `0x18000c93c`
- `0x18000cbb4`
- `0x18000d01c`
- `0x18001f0c4`
- `0x18001f1f0`
- `0x18001f9e4`
- `0x18001fd20`
- `0x18002071c`
- `0x180020820`
- `0x180020b14`
- `0x180020ccc`
- `0x180020e74`
- `0x1800233d0`
- `0x1800236f0`
- `0x180023750`
- `0x1800237b0`
- `0x180023a78`
- `0x180026de0`
- `0x180026fb8`
- `0x180027788`
- `0x180027a68`
- `0x180027f0c`
- `0x18002b078`

## callees

- `0x180010980`

## pseudocode

```c
__int64 __fastcall WPP_SF_D(__int64 a1, unsigned __int16 a2, __int64 a3, int a4)
{
  int v5; // [rsp+68h] [rbp+20h] BYREF

  v5 = a4;
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, int *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           &v5,
           4,
           0);
}

```

## disassembly

```asm
0x180007bd8  mov     r11, rsp
0x180007bdb  mov     [r11+20h], r9d
0x180007bdf  sub     rsp, 48h
0x180007be3  mov     rax, cs:pfnWppTraceMessage
0x180007bea  lea     r9, [r11+20h]
0x180007bee  mov     qword ptr [r11-18h], 0
0x180007bf6  mov     qword ptr [r11-20h], 4
0x180007bfe  mov     [r11-28h], r9
0x180007c02  movzx   r9d, dx
0x180007c06  mov     edx, 2Bh ; '+'
0x180007c0b  call    _guard_dispatch_icall
0x180007c10  add     rsp, 48h
0x180007c14  retn
```
