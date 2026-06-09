# WPP_SF_i

- ea: `0x14000fe04`
- end: `0x14000fe42`
- name: `WPP_SF_i`
- size: `62`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x14000e59c`
- `0x14000e6f4`
- `0x140013b70`
- `0x140014068`
- `0x140015be8`
- `0x1400166d0`
- `0x140016e30`

## callees

- `0x14002c710`

## pseudocode

```c
__int64 WPP_SF_i(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
{
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, __int64 *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           (__int64 *)va,
           8,
           0);
}

```

## disassembly

```asm
0x14000fe04  mov     r11, rsp
0x14000fe07  mov     [r11+20h], r9
0x14000fe0b  sub     rsp, 48h
0x14000fe0f  mov     rax, cs:pfnWppTraceMessage
0x14000fe16  lea     r9, [r11+20h]
0x14000fe1a  mov     qword ptr [r11-18h], 0
0x14000fe22  mov     qword ptr [r11-20h], 8
0x14000fe2a  mov     [r11-28h], r9
0x14000fe2e  movzx   r9d, dx
0x14000fe32  mov     edx, 2Bh ; '+'
0x14000fe37  call    _guard_dispatch_icall
0x14000fe3c  add     rsp, 48h
0x14000fe40  retn
```
