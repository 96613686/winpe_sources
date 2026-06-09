# WPP_SF_

- ea: `0x18002cbac`
- end: `0x18002cbdb`
- name: `WPP_SF_`
- size: `47`
- prototype: ``
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x18002b114`
- `0x18002b304`
- `0x18002b7d4`
- `0x18002bdf4`
- `0x18002c464`
- `0x18002c4f4`
- `0x18002c5e8`
- `0x18002c6b8`
- `0x18002c748`
- `0x18002c7f8`
- `0x18002c8d0`
- `0x18002c9cc`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18002cbc9`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18002cbc9`

## pseudocode

```c
ULONG __fastcall WPP_SF_(TRACEHANDLE a1, USHORT a2)
{
  return TraceMessage(a1, 0x2Bu, &WPP_ef60fab923f6309b270ef1145867690a_Traceguids, a2, 0);
}

```

## disassembly

```asm
0x18002cbac  sub     rsp, 38h
0x18002cbb0  movzx   r9d, dx; MessageNumber
0x18002cbb4  lea     r8, WPP_ef60fab923f6309b270ef1145867690a_Traceguids; MessageGuid
0x18002cbbb  mov     edx, 2Bh ; '+'; MessageFlags
0x18002cbc0  mov     [rsp+38h+var_18], 0
0x18002cbc9  call    cs:__imp_TraceMessage
0x18002cbd0  nop     dword ptr [rax+rax+00h]
0x18002cbd5  add     rsp, 38h
0x18002cbd9  retn
```
