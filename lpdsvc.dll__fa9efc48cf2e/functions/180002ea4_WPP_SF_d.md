# WPP_SF_d

- ea: `0x180002ea4`
- end: `0x180002edb`
- name: `WPP_SF_d`
- size: `55`
- prototype: `ULONG __fastcall(TRACEHANDLE, USHORT, const GUID *, int)`
- caller_count: `17`
- callee_count: `0`
- tags: ``

## callers

- `0x180002974`
- `0x180002b68`
- `0x18000327c`
- `0x180003480`
- `0x180003d4c`
- `0x180005058`
- `0x180006cd8`
- `0x180007354`
- `0x180007810`
- `0x180007a10`
- `0x180007c10`
- `0x180008230`
- `0x180008eb8`
- `0x180009370`
- `0x180009800`
- `0x180009ae4`
- `0x180009c18`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x180002ed0`
- `ADVAPI32!TraceMessage` at `0x180002ed0`

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
0x180002ea4  mov     r11, rsp
0x180002ea7  mov     [r11+20h], r9d
0x180002eab  sub     rsp, 48h
0x180002eaf  mov     qword ptr [r11-18h], 0
0x180002eb7  lea     rax, [r11+20h]
0x180002ebb  movzx   r9d, dx; MessageNumber
0x180002ebf  mov     edx, 2Bh ; '+'; MessageFlags
0x180002ec4  mov     qword ptr [r11-20h], 4
0x180002ecc  mov     [r11-28h], rax
0x180002ed0  call    cs:__imp_TraceMessage
0x180002ed6  add     rsp, 48h
0x180002eda  retn
```
