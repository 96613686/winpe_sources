# WPP_SF_d

- ea: `0x18002bb84`
- end: `0x18002bbc2`
- name: `WPP_SF_d`
- size: `62`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x18002a170`
- `0x18002a350`
- `0x18002a7e0`
- `0x18002adbc`
- `0x18002b7a4`
- `0x18002b87c`
- `0x18002b974`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18002bbb7`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18002bbb7`

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
0x18002bb84  mov     r11, rsp
0x18002bb87  mov     [r11+20h], r9d
0x18002bb8b  sub     rsp, 48h
0x18002bb8f  mov     qword ptr [r11-18h], 0
0x18002bb97  lea     rax, [r11+20h]
0x18002bb9b  movzx   r9d, dx; MessageNumber
0x18002bb9f  lea     r8, WPP_ef60fab923f6309b270ef1145867690a_Traceguids; MessageGuid
0x18002bba6  mov     qword ptr [r11-20h], 4
0x18002bbae  mov     edx, 2Bh ; '+'; MessageFlags
0x18002bbb3  mov     [r11-28h], rax
0x18002bbb7  call    cs:__imp_TraceMessage
0x18002bbbd  add     rsp, 48h
0x18002bbc1  retn
```
