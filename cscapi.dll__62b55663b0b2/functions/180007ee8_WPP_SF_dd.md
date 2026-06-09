# WPP_SF_dd

- ea: `0x180007ee8`
- end: `0x180007f34`
- name: `WPP_SF_dd`
- size: `76`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180004000`
- `0x1800045b0`
- `0x180004cf0`
- `0x180004f10`
- `0x1800052f0`
- `0x1800057f0`
- `0x1800073f0`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180007f29`
- `ntdll!EtwTraceMessage` at `0x180007f29`

## pseudocode

```c
__int64 WPP_SF_dd(__int64 a1, unsigned __int16 a2, __int64 a3, int a4, ...)
{
  int v5; // [rsp+78h] [rbp+20h] BYREF
  va_list va; // [rsp+80h] [rbp+28h] BYREF

  va_start(va, a4);
  v5 = a4;
  return EtwTraceMessage(a1, 43, WPP_00d7c4231f3f33ca0a28c368a7ccec1f_Traceguids, a2, &v5, 4, (__int64 *)va, 4, 0);
}

```

## disassembly

```asm
0x180007ee8  mov     r11, rsp
0x180007eeb  mov     [r11+20h], r9d
0x180007eef  sub     rsp, 58h
0x180007ef3  mov     qword ptr [r11-18h], 0
0x180007efb  lea     rax, [r11+28h]
0x180007eff  mov     r8d, 4
0x180007f05  movzx   r9d, dx
0x180007f09  mov     [r11-20h], r8
0x180007f0d  mov     edx, 2Bh ; '+'
0x180007f12  mov     [r11-28h], rax
0x180007f16  lea     rax, [r11+20h]
0x180007f1a  mov     [r11-30h], r8
0x180007f1e  lea     r8, WPP_00d7c4231f3f33ca0a28c368a7ccec1f_Traceguids
0x180007f25  mov     [r11-38h], rax
0x180007f29  call    cs:__imp_EtwTraceMessage
0x180007f2f  add     rsp, 58h
0x180007f33  retn
```
