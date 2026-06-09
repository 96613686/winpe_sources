# WPP_SF_

- ea: `0x180007bac`
- end: `0x180007bcd`
- name: `WPP_SF_`
- size: `33`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `42`
- callee_count: `0`
- tags: ``

## callers

- `0x180004d50`
- `0x1800056e8`
- `0x180005e5c`
- `0x18000689c`
- `0x180006e50`
- `0x18000701c`
- `0x18000ab90`
- `0x18000af80`
- `0x18000afe0`
- `0x18000bc60`
- `0x18000c080`
- `0x18000c0f0`
- `0x18000c200`
- `0x18000c4a8`
- `0x18000c69c`
- `0x18000ce60`
- `0x18000d660`
- `0x18000e168`
- `0x18000e2b0`
- `0x18000e958`
- `0x18000fb14`
- `0x18000fca0`
- `0x18000fe20`
- `0x180010170`
- `0x1800107e8`
- `0x180011e94`
- `0x180012068`
- `0x180012548`
- `0x180012d38`
- `0x1800133d8`
- `0x1800134e8`
- `0x180013c4c`
- `0x180013dcc`
- `0x1800140ac`
- `0x180014288`
- `0x180014c50`
- `0x180014d60`
- `0x1800171d8`
- `0x180017c60`
- `0x180018350`
- `0x1800183b8`
- `0x180018430`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x180007bc2`
- `ADVAPI32!TraceMessage` at `0x180007bc2`

## pseudocode

```c
ULONG __fastcall WPP_SF_(TRACEHANDLE a1, USHORT a2, const GUID *a3)
{
  return TraceMessage(a1, 0x2Bu, a3, a2, 0);
}

```

## disassembly

```asm
0x180007bac  sub     rsp, 38h
0x180007bb0  movzx   r9d, dx; MessageNumber
0x180007bb4  mov     edx, 2Bh ; '+'; MessageFlags
0x180007bb9  mov     [rsp+38h+var_18], 0
0x180007bc2  call    cs:__imp_TraceMessage
0x180007bc8  add     rsp, 38h
0x180007bcc  retn
```
