# WPP_SF_d

- ea: `0x180008af0`
- end: `0x180008b27`
- name: `WPP_SF_d`
- size: `55`
- prototype: `ULONG __fastcall(TRACEHANDLE, USHORT, const GUID *, int)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x180005a68`
- `0x180006b34`
- `0x18000bb80`
- `0x18000dbd0`
- `0x18000de18`
- `0x18000e1a0`
- `0x18000e430`
- `0x18000e6cc`
- `0x18001048f`
- `0x18001054e`
- `0x180010815`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x180008b1c`
- `ADVAPI32!TraceMessage` at `0x180008b1c`

## pseudocode

```c
ULONG __fastcall WPP_SF_d(TRACEHANDLE a1, USHORT a2, const GUID *a3, int a4)
{
  int v5; // [rsp+68h] [rbp+20h] BYREF

  v5 = a4;
  return TraceMessage(a1, 0x2Bu, a3, a2, &v5, 4, 0);
}

```

## disassembly

```asm
0x180008af0  mov     r11, rsp
0x180008af3  mov     [r11+20h], r9d
0x180008af7  sub     rsp, 48h
0x180008afb  mov     qword ptr [r11-18h], 0
0x180008b03  lea     rax, [r11+20h]
0x180008b07  movzx   r9d, dx; MessageNumber
0x180008b0b  mov     edx, 2Bh ; '+'; MessageFlags
0x180008b10  mov     qword ptr [r11-20h], 4
0x180008b18  mov     [r11-28h], rax
0x180008b1c  call    cs:__imp_TraceMessage
0x180008b22  add     rsp, 48h
0x180008b26  retn
```
