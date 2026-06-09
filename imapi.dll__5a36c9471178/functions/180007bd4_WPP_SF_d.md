# WPP_SF_d

- ea: `0x180007bd4`
- end: `0x180007c0b`
- name: `WPP_SF_d`
- size: `55`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `50`
- callee_count: `0`
- tags: ``

## callers

- `0x180004a40`
- `0x180004d50`
- `0x1800056e8`
- `0x180005e5c`
- `0x1800064e0`
- `0x18000689c`
- `0x180006c20`
- `0x180006d30`
- `0x180006e50`
- `0x18000701c`
- `0x180009e00`
- `0x180009f20`
- `0x18000ab90`
- `0x18000b650`
- `0x18000bc60`
- `0x18000be80`
- `0x18000c0f0`
- `0x18000c200`
- `0x18000c4a8`
- `0x18000cb00`
- `0x18000ce60`
- `0x18000d4d0`
- `0x18000d660`
- `0x18000d830`
- `0x18000e2b0`
- `0x18000e3f0`
- `0x18000e958`
- `0x18000f670`
- `0x18000fa30`
- `0x18000fb14`
- `0x18000fe20`
- `0x1800110a8`
- `0x180011260`
- `0x180011510`
- `0x180011e94`
- `0x180012068`
- `0x180012548`
- `0x180012e0c`
- `0x180013108`
- `0x1800133d8`
- `0x1800134e8`
- `0x1800140ac`
- `0x180014288`
- `0x180014c50`
- `0x1800165b4`
- `0x1800168f8`
- `0x1800171d8`
- `0x180017c60`
- `0x180017f58`
- `0x180018204`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x180007c00`
- `ADVAPI32!TraceMessage` at `0x180007c00`

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
0x180007bd4  mov     r11, rsp
0x180007bd7  mov     [r11+20h], r9d
0x180007bdb  sub     rsp, 48h
0x180007bdf  mov     qword ptr [r11-18h], 0
0x180007be7  lea     rax, [r11+20h]
0x180007beb  movzx   r9d, dx; MessageNumber
0x180007bef  mov     edx, 2Bh ; '+'; MessageFlags
0x180007bf4  mov     qword ptr [r11-20h], 4
0x180007bfc  mov     [r11-28h], rax
0x180007c00  call    cs:__imp_TraceMessage
0x180007c06  add     rsp, 48h
0x180007c0a  retn
```
