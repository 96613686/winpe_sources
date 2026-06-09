# WPP_SF_

- ea: `0x18000fedc`
- end: `0x18000fefd`
- name: `WPP_SF_`
- size: `33`
- prototype: `ULONG __fastcall(TRACEHANDLE, USHORT, const GUID *)`
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x18000de64`
- `0x18000ee64`
- `0x1800143b4`
- `0x18001540c`
- `0x1800160c0`
- `0x1800174a0`
- `0x18001c5f0`
- `0x18001d83b`
- `0x18001d900`
- `0x18001d9d8`
- `0x18001da9d`
- `0x18001daf6`
- `0x18001dbbb`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000fef2`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000fef2`

## pseudocode

```c
ULONG __fastcall WPP_SF_(TRACEHANDLE a1, USHORT a2, const GUID *a3)
{
  return TraceMessage(a1, 0x2Bu, a3, a2, 0);
}

```

## disassembly

```asm
0x18000fedc  sub     rsp, 38h
0x18000fee0  movzx   r9d, dx; MessageNumber
0x18000fee4  mov     edx, 2Bh ; '+'; MessageFlags
0x18000fee9  mov     [rsp+38h+var_18], 0
0x18000fef2  call    cs:__imp_TraceMessage
0x18000fef8  add     rsp, 38h
0x18000fefc  retn
```
