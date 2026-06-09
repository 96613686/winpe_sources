# WPP_SF_s

- ea: `0x18000d2a8`
- end: `0x18000d2de`
- name: `WPP_SF_s`
- size: `54`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a28c`
- `0x18000c5a0`
- `0x18000cf60`
- `0x18000d880`
- `0x18000d9d0`
- `0x18000e340`
- `0x18000e540`
- `0x18000e6e0`
- `0x18000e870`
- `0x18000e9d0`
- `0x18000f198`
- `0x18000f4a0`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x18000d2d3`
- `ADVAPI32!TraceMessage` at `0x18000d2d3`

## pseudocode

```c
ULONG __fastcall WPP_SF_s(TRACEHANDLE a1, USHORT a2, const GUID *a3)
{
  return TraceMessage(a1, 0x2Bu, a3, a2, " ", 2, 0);
}

```

## disassembly

```asm
0x18000d2a8  sub     rsp, 48h
0x18000d2ac  mov     [rsp+48h+var_18], 0
0x18000d2b5  lea     rax, asc_180016AC4; " "
0x18000d2bc  movzx   r9d, dx; MessageNumber
0x18000d2c0  mov     edx, 2Bh ; '+'; MessageFlags
0x18000d2c5  mov     [rsp+48h+var_20], 2
0x18000d2ce  mov     [rsp+48h+var_28], rax
0x18000d2d3  call    cs:__imp_TraceMessage
0x18000d2d9  add     rsp, 48h
0x18000d2dd  retn
```
