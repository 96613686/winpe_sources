# WPP_SF_d

- ea: `0x180005ed4`
- end: `0x180005f0b`
- name: `WPP_SF_d`
- size: `55`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `67`
- callee_count: `0`
- tags: ``

## callers

- `0x180004c90`
- `0x180004e20`
- `0x1800055a0`
- `0x18000568c`
- `0x180005838`
- `0x180005a28`
- `0x180005b6c`
- `0x180006594`
- `0x180006724`
- `0x180006db4`
- `0x18000701c`
- `0x180007288`
- `0x18000d450`
- `0x18000d7e4`
- `0x18000da84`
- `0x18000db44`
- `0x18000dd40`
- `0x18000de40`
- `0x18000dfe4`
- `0x18000e3b4`
- `0x18000e5b0`
- `0x18000e7b0`
- `0x18000e8a8`
- `0x18000ea20`
- `0x18000eaec`
- `0x18000edb0`
- `0x18000ef60`
- `0x18000f1dc`
- `0x18000f3e4`
- `0x18000fd8c`
- `0x1800101a0`
- `0x1800108bc`
- `0x180010970`
- `0x180010bc8`
- `0x180010e30`
- `0x180011040`
- `0x180011310`
- `0x180011510`
- `0x1800115b0`
- `0x1800118a4`
- `0x180011b2c`
- `0x180011cb0`
- `0x180011f58`
- `0x180012060`
- `0x1800122c0`
- `0x1800124a4`
- `0x180012670`
- `0x180012844`
- `0x180012a40`
- `0x180012ce0`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x180005f00`
- `ADVAPI32!TraceMessage` at `0x180005f00`

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
0x180005ed4  mov     r11, rsp
0x180005ed7  mov     [r11+20h], r9d
0x180005edb  sub     rsp, 48h
0x180005edf  mov     qword ptr [r11-18h], 0
0x180005ee7  lea     rax, [r11+20h]
0x180005eeb  movzx   r9d, dx; MessageNumber
0x180005eef  mov     edx, 2Bh ; '+'; MessageFlags
0x180005ef4  mov     qword ptr [r11-20h], 4
0x180005efc  mov     [r11-28h], rax
0x180005f00  call    cs:__imp_TraceMessage
0x180005f06  add     rsp, 48h
0x180005f0a  retn
```
