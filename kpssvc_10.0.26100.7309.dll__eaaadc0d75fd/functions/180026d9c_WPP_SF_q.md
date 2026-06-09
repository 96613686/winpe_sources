# WPP_SF_q

- ea: `0x180026d9c`
- end: `0x180026dd7`
- name: `WPP_SF_q`
- size: `59`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `33`
- callee_count: `0`
- tags: ``

## callers

- `0x18001e520`
- `0x18001e728`
- `0x18001e8e8`
- `0x18001eb40`
- `0x18001edec`
- `0x18001f048`
- `0x18001f5ec`
- `0x18001fd08`
- `0x180020038`
- `0x1800202d0`
- `0x1800203ac`
- `0x1800222f0`
- `0x1800279f8`
- `0x180027af8`
- `0x180027de0`
- `0x180028030`
- `0x1800280d8`
- `0x1800284ec`
- `0x1800285a0`
- `0x180028800`
- `0x1800288c4`
- `0x180028e78`
- `0x180028f28`
- `0x180029038`
- `0x1800290d4`
- `0x1800291e4`
- `0x18002a180`
- `0x18002a2b8`
- `0x18002a42c`
- `0x18002a838`
- `0x18002aae8`
- `0x18002b03c`
- `0x18002d730`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180026dc5`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180026dc5`

## pseudocode

```c
ULONG WPP_SF_q(TRACEHANDLE a1, USHORT a2, const GUID *a3, ...)
{
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  return TraceMessage(a1, 0x2Bu, a3, a2, va, 8, 0);
}

```

## disassembly

```asm
0x180026d9c  mov     r11, rsp
0x180026d9f  mov     [r11+20h], r9
0x180026da3  sub     rsp, 48h
0x180026da7  and     qword ptr [r11-18h], 0
0x180026dac  lea     rax, [r11+20h]
0x180026db0  movzx   r9d, dx; MessageNumber
0x180026db4  mov     edx, 2Bh ; '+'; MessageFlags
0x180026db9  mov     qword ptr [r11-20h], 8
0x180026dc1  mov     [r11-28h], rax
0x180026dc5  call    cs:__imp_TraceMessage
0x180026dcc  nop     dword ptr [rax+rax+00h]
0x180026dd1  add     rsp, 48h
0x180026dd5  retn
```
