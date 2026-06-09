# WPP_SF_q

- ea: `0x180008eb0`
- end: `0x180008eee`
- name: `WPP_SF_q`
- size: `62`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002b70`
- `0x180002db0`
- `0x180003e90`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180008ee3`
- `ntdll!EtwTraceMessage` at `0x180008ee3`

## pseudocode

```c
__int64 WPP_SF_q(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
{
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  return EtwTraceMessage(a1, 43, WPP_daecefe831e93ae5692e249a7442c7d7_Traceguids, a2, (__int64 *)va, 8, 0);
}

```

## disassembly

```asm
0x180008eb0  mov     r11, rsp
0x180008eb3  mov     [r11+20h], r9
0x180008eb7  sub     rsp, 48h
0x180008ebb  mov     qword ptr [r11-18h], 0
0x180008ec3  lea     rax, [r11+20h]
0x180008ec7  movzx   r9d, dx
0x180008ecb  lea     r8, WPP_daecefe831e93ae5692e249a7442c7d7_Traceguids
0x180008ed2  mov     qword ptr [r11-20h], 8
0x180008eda  mov     edx, 2Bh ; '+'
0x180008edf  mov     [r11-28h], rax
0x180008ee3  call    cs:__imp_EtwTraceMessage
0x180008ee9  add     rsp, 48h
0x180008eed  retn
```
