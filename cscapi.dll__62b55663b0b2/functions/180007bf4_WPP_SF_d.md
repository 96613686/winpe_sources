# WPP_SF_d

- ea: `0x180007bf4`
- end: `0x180007c2b`
- name: `WPP_SF_d`
- size: `55`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800036b0`
- `0x180003da0`
- `0x180003f50`
- `0x180004000`
- `0x1800073f0`
- `0x180007950`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180007c20`
- `ntdll!EtwTraceMessage` at `0x180007c20`

## pseudocode

```c
__int64 __fastcall WPP_SF_d(__int64 a1, unsigned __int16 a2, __int64 a3, int a4)
{
  int v5; // [rsp+68h] [rbp+20h] BYREF

  v5 = a4;
  return EtwTraceMessage(a1, 43, a3, a2, &v5, 4, 0);
}

```

## disassembly

```asm
0x180007bf4  mov     r11, rsp
0x180007bf7  mov     [r11+20h], r9d
0x180007bfb  sub     rsp, 48h
0x180007bff  mov     qword ptr [r11-18h], 0
0x180007c07  lea     rax, [r11+20h]
0x180007c0b  movzx   r9d, dx
0x180007c0f  mov     edx, 2Bh ; '+'
0x180007c14  mov     qword ptr [r11-20h], 4
0x180007c1c  mov     [r11-28h], rax
0x180007c20  call    cs:__imp_EtwTraceMessage
0x180007c26  add     rsp, 48h
0x180007c2a  retn
```
