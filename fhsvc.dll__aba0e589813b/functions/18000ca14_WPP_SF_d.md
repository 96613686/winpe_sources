# WPP_SF_d

- ea: `0x18000ca14`
- end: `0x18000ca4b`
- name: `WPP_SF_d`
- size: `55`
- prototype: `ULONG __fastcall(TRACEHANDLE, USHORT, const GUID *, int)`
- caller_count: `51`
- callee_count: `0`
- tags: ``

## callers

- `0x180001200`
- `0x1800012d0`
- `0x180001690`
- `0x1800017c0`
- `0x180001950`
- `0x180001f20`
- `0x180002220`
- `0x180002480`
- `0x1800026a0`
- `0x1800029e0`
- `0x180002f30`
- `0x180003190`
- `0x180003390`
- `0x180003f00`
- `0x180004e80`
- `0x1800062b0`
- `0x1800065c0`
- `0x180006dd0`
- `0x1800079e0`
- `0x180008180`
- `0x1800086e0`
- `0x180008b30`
- `0x180008f90`
- `0x1800093e0`
- `0x1800096c0`
- `0x180009af0`
- `0x18000c130`
- `0x18000c210`
- `0x18000c5d4`
- `0x18000c7b0`
- `0x18000dd60`
- `0x18000df70`
- `0x18000e2f0`
- `0x18000e470`
- `0x18000e520`
- `0x18000e5d0`
- `0x18000e740`
- `0x18000e8b0`
- `0x180010894`
- `0x1800109d4`
- `0x180011ba0`
- `0x180011c50`
- `0x180011ce0`
- `0x180011db8`
- `0x180011e12`
- `0x180011ea3`
- `0x180011fb0`
- `0x180012386`
- `0x180012422`
- `0x180012491`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x18000ca40`
- `ADVAPI32!TraceMessage` at `0x18000ca40`

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
0x18000ca14  mov     r11, rsp
0x18000ca17  mov     [r11+20h], r9d
0x18000ca1b  sub     rsp, 48h
0x18000ca1f  mov     qword ptr [r11-18h], 0
0x18000ca27  lea     rax, [r11+20h]
0x18000ca2b  movzx   r9d, dx; MessageNumber
0x18000ca2f  mov     edx, 2Bh ; '+'; MessageFlags
0x18000ca34  mov     qword ptr [r11-20h], 4
0x18000ca3c  mov     [r11-28h], rax
0x18000ca40  call    cs:__imp_TraceMessage
0x18000ca46  add     rsp, 48h
0x18000ca4a  retn
```
