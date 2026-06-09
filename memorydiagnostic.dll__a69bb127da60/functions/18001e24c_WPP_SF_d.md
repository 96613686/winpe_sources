# WPP_SF_d

- ea: `0x18001e24c`
- end: `0x18001e28a`
- name: `WPP_SF_d`
- size: `62`
- prototype: `ULONG __fastcall(TRACEHANDLE, USHORT, __int64, int)`
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x18001a3e4`
- `0x18001a5a0`
- `0x18001aa94`
- `0x18001bcd0`
- `0x18001be90`
- `0x18001c100`
- `0x18001c310`
- `0x18001cae4`
- `0x18001cd88`
- `0x18001d094`
- `0x18001d250`
- `0x18001d378`
- `0x18001d7a0`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x18001e27f`
- `ADVAPI32!TraceMessage` at `0x18001e27f`

## pseudocode

```c
ULONG __fastcall WPP_SF_d(TRACEHANDLE a1, USHORT a2, __int64 a3, int a4)
{
  int v5; // [rsp+68h] [rbp+20h] BYREF

  v5 = a4;
  return TraceMessage(a1, 0x2Bu, &WPP_8ba4b6a669b233c65d537f5d7489fdc1_Traceguids, a2, &v5, 4, 0);
}

```

## disassembly

```asm
0x18001e24c  mov     r11, rsp
0x18001e24f  mov     [r11+20h], r9d
0x18001e253  sub     rsp, 48h
0x18001e257  mov     qword ptr [r11-18h], 0
0x18001e25f  lea     rax, [r11+20h]
0x18001e263  movzx   r9d, dx; MessageNumber
0x18001e267  lea     r8, WPP_8ba4b6a669b233c65d537f5d7489fdc1_Traceguids; MessageGuid
0x18001e26e  mov     qword ptr [r11-20h], 4
0x18001e276  mov     edx, 2Bh ; '+'; MessageFlags
0x18001e27b  mov     [r11-28h], rax
0x18001e27f  call    cs:__imp_TraceMessage
0x18001e285  add     rsp, 48h
0x18001e289  retn
```
