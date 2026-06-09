# WPP_SF_sD

- ea: `0x1800047ac`
- end: `0x1800047f2`
- name: `WPP_SF_sD`
- size: `70`
- prototype: `__int64(__int64, unsigned __int16, __int64, __int64, ...)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800027b0`
- `0x180004b30`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x1800047e7`
- `ntdll!EtwTraceMessage` at `0x1800047e7`

## pseudocode

```c
__int64 WPP_SF_sD(__int64 a1, unsigned __int16 a2, __int64 a3, __int64 a4, ...)
{
  va_list va; // [rsp+80h] [rbp+28h] BYREF

  va_start(va, a4);
  return EtwTraceMessage(a1, 43, a3, a2, " ", 2, (__int64 *)va);
}

```

## disassembly

```asm
0x1800047ac  mov     r11, rsp
0x1800047af  sub     rsp, 58h
0x1800047b3  mov     qword ptr [r11-18h], 0
0x1800047bb  lea     rax, [r11+28h]
0x1800047bf  mov     qword ptr [r11-20h], 4
0x1800047c7  mov     [r11-28h], rax
0x1800047cb  lea     rax, asc_180007748; " "
0x1800047d2  movzx   r9d, dx
0x1800047d6  mov     edx, 2Bh ; '+'
0x1800047db  mov     qword ptr [r11-30h], 2
0x1800047e3  mov     [r11-38h], rax
0x1800047e7  call    cs:__imp_EtwTraceMessage
0x1800047ed  add     rsp, 58h
0x1800047f1  retn
```
