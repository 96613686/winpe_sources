# WPP_SF_q

- ea: `0x180021fd4`
- end: `0x180022012`
- name: `WPP_SF_q`
- size: `62`
- prototype: ``
- caller_count: `73`
- callee_count: `0`
- tags: ``

## callers

- `0x1800029d0`
- `0x180002ef0`
- `0x180011f80`
- `0x1800121b4`
- `0x180012240`
- `0x180013f40`
- `0x180016ba0`
- `0x180016df0`
- `0x180016ec0`
- `0x180016fd0`
- `0x1800171c0`
- `0x1800172d0`
- `0x1800173e0`
- `0x1800174b0`
- `0x1800175d0`
- `0x180017920`
- `0x1800179f0`
- `0x180017cb0`
- `0x180017e20`
- `0x180017f80`
- `0x1800180b0`
- `0x1800181d0`
- `0x1800187a0`
- `0x180018c90`
- `0x180018da0`
- `0x180018eb0`
- `0x180019390`
- `0x180019470`
- `0x180019890`
- `0x180019980`
- `0x180019aa0`
- `0x180019cb0`
- `0x180019eb0`
- `0x180019f90`
- `0x18001a0c0`
- `0x18001a1f0`
- `0x18001a3e0`
- `0x18001a4c0`
- `0x18001a7a0`
- `0x18001aa40`
- `0x18001ab70`
- `0x18001ac80`
- `0x18001adf0`
- `0x18001b550`
- `0x18001b660`
- `0x18001b920`
- `0x18001ba50`
- `0x18001bb70`
- `0x18001bda0`
- `0x18001beb0`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180022000`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180022000`

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
0x180021fd4  mov     r11, rsp
0x180021fd7  mov     [r11+20h], r9
0x180021fdb  sub     rsp, 48h
0x180021fdf  mov     qword ptr [r11-18h], 0
0x180021fe7  lea     rax, [r11+20h]
0x180021feb  movzx   r9d, dx; MessageNumber
0x180021fef  mov     edx, 2Bh ; '+'; MessageFlags
0x180021ff4  mov     qword ptr [r11-20h], 8
0x180021ffc  mov     [r11-28h], rax
0x180022000  call    cs:__imp_TraceMessage
0x180022007  nop     dword ptr [rax+rax+00h]
0x18002200c  add     rsp, 48h
0x180022010  retn
```
