# WPP_SF_

- ea: `0x180005eac`
- end: `0x180005ecd`
- name: `WPP_SF_`
- size: `33`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `84`
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
- `0x180006ce8`
- `0x180006db4`
- `0x180006ef0`
- `0x18000701c`
- `0x1800071e8`
- `0x180007288`
- `0x18000d450`
- `0x18000d7e4`
- `0x18000da84`
- `0x18000db44`
- `0x18000dd40`
- `0x18000de40`
- `0x18000dfe4`
- `0x18000e314`
- `0x18000e3b4`
- `0x18000e5b0`
- `0x18000e7b0`
- `0x18000e8a8`
- `0x18000ea20`
- `0x18000eaec`
- `0x18000edb0`
- `0x18000ef60`
- `0x18000f1dc`
- `0x18000f2c4`
- `0x18000f3e4`
- `0x18000fd8c`
- `0x1800101a0`
- `0x180010574`
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

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x180005ec2`
- `ADVAPI32!TraceMessage` at `0x180005ec2`

## pseudocode

```c
ULONG __fastcall WPP_SF_(TRACEHANDLE a1, USHORT a2, const GUID *a3)
{
  return TraceMessage(a1, 0x2Bu, a3, a2, 0);
}

```

## disassembly

```asm
0x180005eac  sub     rsp, 38h
0x180005eb0  movzx   r9d, dx; MessageNumber
0x180005eb4  mov     edx, 2Bh ; '+'; MessageFlags
0x180005eb9  mov     [rsp+38h+var_18], 0
0x180005ec2  call    cs:__imp_TraceMessage
0x180005ec8  add     rsp, 38h
0x180005ecc  retn
```
