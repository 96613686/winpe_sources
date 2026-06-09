# WPP_SF_dD

- ea: `0x180002eec`
- end: `0x180002f38`
- name: `WPP_SF_dD`
- size: `76`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001d60`
- `0x180002560`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180002f2d`
- `ntdll!EtwTraceMessage` at `0x180002f2d`

## pseudocode

```c
__int64 __fastcall WPP_SF_dD(__int64 a1, unsigned __int16 a2, __int64 a3, int a4)
{
  int v5; // [rsp+78h] [rbp+20h] BYREF

  v5 = a4;
  return EtwTraceMessage(a1, 43, WPP_f9f245b695a1313fa77432e2631acac1_Traceguids, a2, &v5);
}

```

## disassembly

```asm
0x180002eec  mov     r11, rsp
0x180002eef  mov     [r11+20h], r9d
0x180002ef3  sub     rsp, 58h
0x180002ef7  mov     qword ptr [r11-18h], 0
0x180002eff  lea     rax, [r11+28h]
0x180002f03  mov     r8d, 4
0x180002f09  movzx   r9d, dx
0x180002f0d  mov     [r11-20h], r8
0x180002f11  mov     edx, 2Bh ; '+'
0x180002f16  mov     [r11-28h], rax
0x180002f1a  lea     rax, [r11+20h]
0x180002f1e  mov     [r11-30h], r8
0x180002f22  lea     r8, WPP_f9f245b695a1313fa77432e2631acac1_Traceguids
0x180002f29  mov     [r11-38h], rax
0x180002f2d  call    cs:__imp_EtwTraceMessage
0x180002f33  add     rsp, 58h
0x180002f37  retn
```
