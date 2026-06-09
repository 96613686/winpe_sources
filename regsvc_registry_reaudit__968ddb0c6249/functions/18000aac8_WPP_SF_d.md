# WPP_SF_d

- ea: `0x18000aac8`
- end: `0x18000aaff`
- name: `WPP_SF_d`
- size: `55`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `16`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180004f00`
- `0x180006ae0`
- `0x180008c30`
- `0x1800093a8`
- `0x18000a190`
- `0x18000a2a4`
- `0x18000a7b8`
- `0x18000ae4c`
- `0x18000bf38`
- `0x18000c134`
- `0x18000e1a8`
- `0x180010430`
- `0x180011c7c`
- `0x180011d10`
- `0x1800136b0`
- `0x180015250`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18000aaf4`
- `ntdll!EtwTraceMessage` at `0x18000aaf4`

## pseudocode

```c
__int64 __fastcall WPP_SF_d(__int64 a1, unsigned __int16 a2, __int64 a3, int a4)
{
  int v5; // [rsp+68h] [rbp+20h] BYREF

  v5 = a4;
  return EtwTraceMessage(a1, 43, a3, a2, &v5);
}

```

## disassembly

```asm
0x18000aac8  mov     r11, rsp
0x18000aacb  mov     [r11+20h], r9d
0x18000aacf  sub     rsp, 48h
0x18000aad3  mov     qword ptr [r11-18h], 0
0x18000aadb  lea     rax, [r11+20h]
0x18000aadf  movzx   r9d, dx
0x18000aae3  mov     edx, 2Bh ; '+'
0x18000aae8  mov     qword ptr [r11-20h], 4
0x18000aaf0  mov     [r11-28h], rax
0x18000aaf4  call    cs:__imp_EtwTraceMessage
0x18000aafa  add     rsp, 48h
0x18000aafe  retn
```
