# WPP_SF_q

- ea: `0x18000ffa4`
- end: `0x18000ffdb`
- name: `WPP_SF_q`
- size: `55`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x180001414`
- `0x1800032c0`
- `0x1800038e0`
- `0x18000a020`
- `0x18000a160`
- `0x18000bf1c`
- `0x18000c7d0`
- `0x180014150`
- `0x180016db0`
- `0x180016f70`
- `0x180017f00`
- `0x180019200`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000ffd0`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000ffd0`

## pseudocode

```c
ULONG WPP_SF_q(TRACEHANDLE a1, USHORT a2, const GUID *a3, ...)
{
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  return TraceMessage(a1, 0x2Bu, a3, a2, va, 8, 0);
}

```

## disassembly

```asm
0x18000ffa4  mov     r11, rsp
0x18000ffa7  mov     [r11+20h], r9
0x18000ffab  sub     rsp, 48h
0x18000ffaf  mov     qword ptr [r11-18h], 0
0x18000ffb7  lea     rax, [r11+20h]
0x18000ffbb  movzx   r9d, dx; MessageNumber
0x18000ffbf  mov     edx, 2Bh ; '+'; MessageFlags
0x18000ffc4  mov     qword ptr [r11-20h], 8
0x18000ffcc  mov     [r11-28h], rax
0x18000ffd0  call    cs:__imp_TraceMessage
0x18000ffd6  add     rsp, 48h
0x18000ffda  retn
```
