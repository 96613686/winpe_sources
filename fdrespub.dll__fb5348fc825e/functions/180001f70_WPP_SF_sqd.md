# WPP_SF_sqd

- ea: `0x180001f70`
- end: `0x180001fc6`
- name: `WPP_SF_sqd`
- size: `86`
- prototype: `__int64(__int64, unsigned __int16, __int64, __int64, ...)`
- caller_count: `12`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001b20`
- `0x180001bf0`
- `0x180001cc0`
- `0x180001e60`
- `0x1800020f8`
- `0x1800022b4`
- `0x1800027b0`
- `0x180002ad0`
- `0x180002f24`
- `0x1800036b0`
- `0x180003898`
- `0x180004220`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180001fbb`
- `ntdll!EtwTraceMessage` at `0x180001fbb`

## pseudocode

```c
__int64 WPP_SF_sqd(__int64 a1, unsigned __int16 a2, __int64 a3, __int64 a4, ...)
{
  va_list va; // [rsp+90h] [rbp+28h] BYREF

  va_start(va, a4);
  return EtwTraceMessage(a1, 43, a3, a2, " ", 2, (__int64 *)va);
}

```

## disassembly

```asm
0x180001f70  mov     r11, rsp
0x180001f73  sub     rsp, 68h
0x180001f77  mov     qword ptr [r11-18h], 0
0x180001f7f  lea     rax, [r11+30h]
0x180001f83  mov     qword ptr [r11-20h], 4
0x180001f8b  mov     [r11-28h], rax
0x180001f8f  lea     rax, [r11+28h]
0x180001f93  mov     qword ptr [r11-30h], 8
0x180001f9b  mov     [r11-38h], rax
0x180001f9f  lea     rax, asc_180007748; " "
0x180001fa6  movzx   r9d, dx
0x180001faa  mov     edx, 2Bh ; '+'
0x180001faf  mov     qword ptr [r11-40h], 2
0x180001fb7  mov     [r11-48h], rax
0x180001fbb  call    cs:__imp_EtwTraceMessage
0x180001fc1  add     rsp, 68h
0x180001fc5  retn
```
