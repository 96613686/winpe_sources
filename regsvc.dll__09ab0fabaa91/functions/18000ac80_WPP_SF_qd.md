# WPP_SF_qd

- ea: `0x18000ac80`
- end: `0x18000acc7`
- name: `WPP_SF_qd`
- size: `71`
- prototype: `__int64(__int64, unsigned __int16, __int64, ...)`
- caller_count: `5`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180008c30`
- `0x18000a2a4`
- `0x18000b6d4`
- `0x18000b8a0`
- `0x18000c424`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18000acbc`
- `ntdll!EtwTraceMessage` at `0x18000acbc`

## pseudocode

```c
__int64 WPP_SF_qd(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
{
  va_list va; // [rsp+78h] [rbp+20h] BYREF

  va_start(va, a3);
  return EtwTraceMessage(a1, 43, a3, a2, (__int64 *)va);
}

```

## disassembly

```asm
0x18000ac80  mov     r11, rsp
0x18000ac83  mov     [r11+20h], r9
0x18000ac87  sub     rsp, 58h
0x18000ac8b  mov     qword ptr [r11-18h], 0
0x18000ac93  lea     rax, [r11+28h]
0x18000ac97  mov     qword ptr [r11-20h], 4
0x18000ac9f  mov     [r11-28h], rax
0x18000aca3  lea     rax, [r11+20h]
0x18000aca7  movzx   r9d, dx
0x18000acab  mov     edx, 2Bh ; '+'
0x18000acb0  mov     qword ptr [r11-30h], 8
0x18000acb8  mov     [r11-38h], rax
0x18000acbc  call    cs:__imp_EtwTraceMessage
0x18000acc2  add     rsp, 58h
0x18000acc6  retn
```
