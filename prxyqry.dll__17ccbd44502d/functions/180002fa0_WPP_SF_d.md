# WPP_SF_d

- ea: `0x180002fa0`
- end: `0x180002fe5`
- name: `WPP_SF_d`
- size: `69`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800014bc`
- `0x180001db0`
- `0x1800021c0`
- `0x180002660`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180002fd3`
- `ntdll!EtwTraceMessage` at `0x180002fd3`

## pseudocode

```c
__int64 __fastcall WPP_SF_d(__int64 a1, unsigned __int16 a2, __int64 a3, int a4)
{
  int v5; // [rsp+68h] [rbp+20h] BYREF

  v5 = a4;
  return EtwTraceMessage(a1, 43, WPP_f9f245b695a1313fa77432e2631acac1_Traceguids, a2, &v5, 4, 0);
}

```

## disassembly

```asm
0x180002fa0  mov     r11, rsp
0x180002fa3  mov     [r11+20h], r9d
0x180002fa7  sub     rsp, 48h
0x180002fab  mov     qword ptr [r11-18h], 0
0x180002fb3  lea     rax, [r11+20h]
0x180002fb7  movzx   r9d, dx
0x180002fbb  lea     r8, WPP_f9f245b695a1313fa77432e2631acac1_Traceguids
0x180002fc2  mov     qword ptr [r11-20h], 4
0x180002fca  mov     edx, 2Bh ; '+'
0x180002fcf  mov     [r11-28h], rax
0x180002fd3  call    cs:__imp_EtwTraceMessage
0x180002fda  nop     dword ptr [rax+rax+00h]
0x180002fdf  add     rsp, 48h
0x180002fe3  retn
```
