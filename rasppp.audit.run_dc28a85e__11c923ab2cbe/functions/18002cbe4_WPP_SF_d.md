# WPP_SF_d

- ea: `0x18002cbe4`
- end: `0x18002cc29`
- name: `WPP_SF_d`
- size: `69`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x18002b114`
- `0x18002b304`
- `0x18002b7d4`
- `0x18002bdf4`
- `0x18002c7f8`
- `0x18002c8d0`
- `0x18002c9cc`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18002cc17`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18002cc17`

## pseudocode

```c
ULONG __fastcall WPP_SF_d(TRACEHANDLE a1, USHORT a2, __int64 a3, int a4)
{
  int v5; // [rsp+68h] [rbp+20h] BYREF

  v5 = a4;
  return TraceMessage(a1, 0x2Bu, &WPP_ef60fab923f6309b270ef1145867690a_Traceguids, a2, &v5, 4, 0);
}

```

## disassembly

```asm
0x18002cbe4  mov     r11, rsp
0x18002cbe7  mov     [r11+20h], r9d
0x18002cbeb  sub     rsp, 48h
0x18002cbef  mov     qword ptr [r11-18h], 0
0x18002cbf7  lea     rax, [r11+20h]
0x18002cbfb  movzx   r9d, dx; MessageNumber
0x18002cbff  lea     r8, WPP_ef60fab923f6309b270ef1145867690a_Traceguids; MessageGuid
0x18002cc06  mov     qword ptr [r11-20h], 4
0x18002cc0e  mov     edx, 2Bh ; '+'; MessageFlags
0x18002cc13  mov     [r11-28h], rax
0x18002cc17  call    cs:__imp_TraceMessage
0x18002cc1e  nop     dword ptr [rax+rax+00h]
0x18002cc23  add     rsp, 48h
0x18002cc27  retn
```
