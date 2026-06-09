# WPP_SF_DDD

- ea: `0x1400029cc`
- end: `0x140002a23`
- name: `WPP_SF_DDD`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140002784`
- `0x140002ea0`

## callees

- `0x140003e00`

## pseudocode

```c
__int64 __fastcall WPP_SF_DDD(__int64 a1, unsigned __int16 a2, __int64 a3, int a4, int a5, int a6)
{
  int v7; // [rsp+88h] [rbp+20h] BYREF

  v7 = a4;
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, int *, __int64, int *, __int64, int *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           &v7,
           4,
           &a5,
           4,
           &a6,
           4,
           0);
}

```

## disassembly

```asm
0x1400029cc  mov     r11, rsp
0x1400029cf  mov     [r11+20h], r9d
0x1400029d3  sub     rsp, 68h
0x1400029d7  mov     rax, cs:pfnWppTraceMessage
0x1400029de  lea     r9, [r11+30h]
0x1400029e2  mov     qword ptr [r11-18h], 0
0x1400029ea  mov     r10d, 4
0x1400029f0  mov     [r11-20h], r10
0x1400029f4  mov     [r11-28h], r9
0x1400029f8  lea     r9, [r11+28h]
0x1400029fc  mov     [r11-30h], r10
0x140002a00  mov     [r11-38h], r9
0x140002a04  lea     r9, [r11+20h]
0x140002a08  mov     [r11-40h], r10
0x140002a0c  mov     [r11-48h], r9
0x140002a10  movzx   r9d, dx
0x140002a14  lea     edx, [r10+27h]
0x140002a18  call    _guard_dispatch_icall
0x140002a1d  add     rsp, 68h
0x140002a21  retn
```
