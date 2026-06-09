# WPP_SF_s

- ea: `0x18003b0a0`
- end: `0x18003b0de`
- name: `WPP_SF_s`
- size: `62`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180039908`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18003b0d3`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18003b0d3`

## string_xrefs

- `0x18003b0b3`: `Pku2uGetContainerUserToken`

## pseudocode

```c
ULONG __fastcall WPP_SF_s(TRACEHANDLE a1)
{
  return TraceMessage(
           a1,
           0x2Bu,
           &WPP_c43b604716f332f766453d0e055ebcf6_Traceguids,
           0x19u,
           "Pku2uGetContainerUserToken",
           27,
           0);
}

```

## disassembly

```asm
0x18003b0a0  sub     rsp, 48h
0x18003b0a4  mov     r9d, 19h; MessageNumber
0x18003b0aa  mov     [rsp+48h+var_18], 0
0x18003b0b3  lea     rax, aPku2ugetcontai; "Pku2uGetContainerUserToken"
0x18003b0ba  mov     [rsp+48h+var_20], 1Bh
0x18003b0c3  lea     r8, WPP_c43b604716f332f766453d0e055ebcf6_Traceguids; MessageGuid
0x18003b0ca  mov     [rsp+48h+var_28], rax
0x18003b0cf  lea     edx, [r9+12h]; MessageFlags
0x18003b0d3  call    cs:__imp_TraceMessage
0x18003b0d9  add     rsp, 48h
0x18003b0dd  retn
```
