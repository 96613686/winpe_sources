# WPP_SF_d

- ea: `0x1400021bc`
- end: `0x1400021fa`
- name: `WPP_SF_d`
- size: `62`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `125`
- callee_count: `1`
- tags: ``

## callers

- `0x140001640`
- `0x140001a24`
- `0x140001c90`
- `0x140001f80`
- `0x140002260`
- `0x1400027d0`
- `0x140002b38`
- `0x140004af0`
- `0x140004f34`
- `0x14000540c`
- `0x140005780`
- `0x1400058c0`
- `0x140005a90`
- `0x140005bc0`
- `0x140005d10`
- `0x140006260`
- `0x1400065b4`
- `0x140006c08`
- `0x140006f00`
- `0x1400078cc`
- `0x140007ca0`
- `0x140008a54`
- `0x140009a00`
- `0x14000adb8`
- `0x14000b5a8`
- `0x14000bd80`
- `0x14000be20`
- `0x14000bed0`
- `0x14000c49c`
- `0x14000c9b8`
- `0x14000ccc8`
- `0x14000cf88`
- `0x14000d318`
- `0x14000d8b0`
- `0x14000e378`
- `0x14000e988`
- `0x14000f2a4`
- `0x14000f6cc`
- `0x14000fe9c`
- `0x140010054`
- `0x1400101b8`
- `0x140010404`
- `0x14001066c`
- `0x140010a00`
- `0x140010f60`
- `0x140011264`
- `0x14001169c`
- `0x140011e00`
- `0x1400123a8`
- `0x1400128ec`

## callees

- `0x14002c710`

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
0x1400021bc  mov     r11, rsp
0x1400021bf  mov     [r11+20h], r9d
0x1400021c3  sub     rsp, 48h
0x1400021c7  mov     rax, cs:pfnWppTraceMessage
0x1400021ce  lea     r9, [r11+20h]
0x1400021d2  mov     qword ptr [r11-18h], 0
0x1400021da  mov     qword ptr [r11-20h], 4
0x1400021e2  mov     [r11-28h], r9
0x1400021e6  movzx   r9d, dx
0x1400021ea  mov     edx, 2Bh ; '+'
0x1400021ef  call    _guard_dispatch_icall
0x1400021f4  add     rsp, 48h
0x1400021f8  retn
```
