# WPP_SF_q

- ea: `0x180008ce0`
- end: `0x180008d17`
- name: `WPP_SF_q`
- size: `55`
- prototype: ``
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180002e18`
- `0x1800036d4`
- `0x180004178`
- `0x180004374`
- `0x180004418`
- `0x1800044bc`
- `0x180009f04`
- `0x18000a468`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x180008d0c`
- `ADVAPI32!TraceMessage` at `0x180008d0c`

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
0x180008ce0  mov     r11, rsp
0x180008ce3  mov     [r11+20h], r9
0x180008ce7  sub     rsp, 48h
0x180008ceb  mov     qword ptr [r11-18h], 0
0x180008cf3  lea     rax, [r11+20h]
0x180008cf7  movzx   r9d, dx; MessageNumber
0x180008cfb  mov     edx, 2Bh ; '+'; MessageFlags
0x180008d00  mov     qword ptr [r11-20h], 8
0x180008d08  mov     [r11-28h], rax
0x180008d0c  call    cs:__imp_TraceMessage
0x180008d12  add     rsp, 48h
0x180008d16  retn
```
