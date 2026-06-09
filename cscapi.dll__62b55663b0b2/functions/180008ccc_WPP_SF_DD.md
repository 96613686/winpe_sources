# WPP_SF_DD

- ea: `0x180008ccc`
- end: `0x180008d18`
- name: `WPP_SF_DD`
- size: `76`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002db0`
- `0x1800036b0`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180008d0d`
- `ntdll!EtwTraceMessage` at `0x180008d0d`

## pseudocode

```c
__int64 WPP_SF_DD(__int64 a1, unsigned __int16 a2, __int64 a3, int a4, ...)
{
  int v5; // [rsp+78h] [rbp+20h] BYREF
  va_list va; // [rsp+80h] [rbp+28h] BYREF

  va_start(va, a4);
  v5 = a4;
  return EtwTraceMessage(a1, 43, WPP_daecefe831e93ae5692e249a7442c7d7_Traceguids, a2, &v5, 4, (__int64 *)va);
}

```

## disassembly

```asm
0x180008ccc  mov     r11, rsp
0x180008ccf  mov     [r11+20h], r9d
0x180008cd3  sub     rsp, 58h
0x180008cd7  mov     qword ptr [r11-18h], 0
0x180008cdf  lea     rax, [r11+28h]
0x180008ce3  mov     r8d, 4
0x180008ce9  movzx   r9d, dx
0x180008ced  mov     [r11-20h], r8
0x180008cf1  mov     edx, 2Bh ; '+'
0x180008cf6  mov     [r11-28h], rax
0x180008cfa  lea     rax, [r11+20h]
0x180008cfe  mov     [r11-30h], r8
0x180008d02  lea     r8, WPP_daecefe831e93ae5692e249a7442c7d7_Traceguids
0x180008d09  mov     [r11-38h], rax
0x180008d0d  call    cs:__imp_EtwTraceMessage
0x180008d13  add     rsp, 58h
0x180008d17  retn
```
