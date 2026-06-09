# WPP_SF_D

- ea: `0x14000eb54`
- end: `0x14000eb92`
- name: `WPP_SF_D`
- size: `62`
- prototype: ``
- caller_count: `19`
- callee_count: `1`
- tags: ``

## callers

- `0x1400010e0`
- `0x140009240`
- `0x140009350`
- `0x14000d284`
- `0x14000d708`
- `0x14000d8b8`
- `0x14001d008`
- `0x14001d708`
- `0x14001d7cc`
- `0x14001d8b0`
- `0x14001e00c`
- `0x14001e2dc`
- `0x14001e4dc`
- `0x14001ee0c`
- `0x14001f4b0`
- `0x14001f8b0`
- `0x14001fae4`
- `0x14001fc20`
- `0x14001fd60`

## callees

- `0x140013150`

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
0x14000eb54  mov     r11, rsp
0x14000eb57  mov     [r11+20h], r9d
0x14000eb5b  sub     rsp, 48h
0x14000eb5f  mov     rax, cs:pfnWppTraceMessage
0x14000eb66  lea     r9, [r11+20h]
0x14000eb6a  mov     qword ptr [r11-18h], 0
0x14000eb72  mov     qword ptr [r11-20h], 4
0x14000eb7a  mov     [r11-28h], r9
0x14000eb7e  movzx   r9d, dx
0x14000eb82  mov     edx, 2Bh ; '+'
0x14000eb87  call    _guard_dispatch_icall
0x14000eb8c  add     rsp, 48h
0x14000eb90  retn
```
