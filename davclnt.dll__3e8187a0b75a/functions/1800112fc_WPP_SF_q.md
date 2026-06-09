# WPP_SF_q

- ea: `0x1800112fc`
- end: `0x18001133a`
- name: `WPP_SF_q`
- size: `62`
- prototype: `__int64(__int64, unsigned __int16, __int64, ...)`
- caller_count: `5`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001600`
- `0x180002970`
- `0x180004340`
- `0x180006c50`
- `0x1800070c0`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18001132f`
- `ntdll!EtwTraceMessage` at `0x18001132f`

## pseudocode

```c
__int64 WPP_SF_q(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
{
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  return EtwTraceMessage(a1, 43, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, a2, (__int64 *)va);
}

```

## disassembly

```asm
0x1800112fc  mov     r11, rsp
0x1800112ff  mov     [r11+20h], r9
0x180011303  sub     rsp, 48h
0x180011307  mov     qword ptr [r11-18h], 0
0x18001130f  lea     rax, [r11+20h]
0x180011313  movzx   r9d, dx
0x180011317  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18001131e  mov     qword ptr [r11-20h], 8
0x180011326  mov     edx, 2Bh ; '+'
0x18001132b  mov     [r11-28h], rax
0x18001132f  call    cs:__imp_EtwTraceMessage
0x180011335  add     rsp, 48h
0x180011339  retn
```
