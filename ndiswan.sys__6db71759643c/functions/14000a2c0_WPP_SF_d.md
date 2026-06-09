# WPP_SF_d

- ea: `0x14000a2c0`
- end: `0x14000a2fe`
- name: `WPP_SF_d`
- size: `62`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `52`
- callee_count: `1`
- tags: ``

## callers

- `0x140001010`
- `0x1400019a0`
- `0x140001be0`
- `0x140002770`
- `0x1400042e0`
- `0x1400048c0`
- `0x140004be0`
- `0x1400063a0`
- `0x140006640`
- `0x140007560`
- `0x140007fb0`
- `0x14000c6e0`
- `0x14000ce70`
- `0x14000d310`
- `0x14000e8b0`
- `0x14000e980`
- `0x14000ef64`
- `0x14000f870`
- `0x140010150`
- `0x140010640`
- `0x140010a1c`
- `0x140010b40`
- `0x140011850`
- `0x140024a80`
- `0x140025c80`
- `0x140025fa0`
- `0x140026220`
- `0x1400262c0`
- `0x140026c80`
- `0x140027a50`
- `0x140028610`
- `0x14002b270`
- `0x14002c6a0`
- `0x14002c7c0`
- `0x14002d170`
- `0x14002d324`
- `0x14002d730`
- `0x14002dc9c`
- `0x14002eed4`
- `0x14002f620`
- `0x1400305b0`
- `0x140030940`
- `0x140030e70`
- `0x140031b80`
- `0x140032340`
- `0x140032ba0`
- `0x140032cd0`
- `0x1400330a0`
- `0x1400359f4`
- `0x140035ad8`

## callees

- `0x140016230`

## pseudocode

```c
__int64 __fastcall WPP_SF_d(__int64 a1, unsigned __int16 a2, __int64 a3, int a4)
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
0x14000a2c0  mov     r11, rsp
0x14000a2c3  mov     [r11+20h], r9d
0x14000a2c7  sub     rsp, 48h
0x14000a2cb  mov     rax, cs:pfnWppTraceMessage
0x14000a2d2  lea     r9, [r11+20h]
0x14000a2d6  mov     qword ptr [r11-18h], 0
0x14000a2de  mov     qword ptr [r11-20h], 4
0x14000a2e6  mov     [r11-28h], r9
0x14000a2ea  movzx   r9d, dx
0x14000a2ee  mov     edx, 2Bh ; '+'
0x14000a2f3  call    _guard_dispatch_icall
0x14000a2f8  add     rsp, 48h
0x14000a2fc  retn
```
