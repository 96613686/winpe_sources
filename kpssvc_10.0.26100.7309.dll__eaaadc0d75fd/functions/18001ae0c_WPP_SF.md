# WPP_SF_

- ea: `0x18001ae0c`
- end: `0x18001ae31`
- name: `WPP_SF_`
- size: `37`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `47`
- callee_count: `0`
- tags: ``

## callers

- `0x180019a20`
- `0x180019ad0`
- `0x180019dcc`
- `0x18001a0c0`
- `0x18001a1e0`
- `0x18001a868`
- `0x18001a958`
- `0x18001aa80`
- `0x18001e520`
- `0x1800203ac`
- `0x180020610`
- `0x1800208d8`
- `0x1800215c0`
- `0x1800216f4`
- `0x180021828`
- `0x180021b10`
- `0x18002786c`
- `0x180028e78`
- `0x180028f28`
- `0x180029038`
- `0x1800290d4`
- `0x1800291e4`
- `0x180029e64`
- `0x18002a080`
- `0x18002a5a8`
- `0x18002b24c`
- `0x18002b4e0`
- `0x18002c99c`
- `0x18002ccd0`
- `0x18002cf60`
- `0x18002d730`
- `0x18002d9ac`
- `0x18002dbb8`
- `0x18002dc4c`
- `0x18002dd00`
- `0x18002e1f0`
- `0x18002e330`
- `0x18002e7f8`
- `0x18002ea8c`
- `0x18002ed24`
- `0x18002f194`
- `0x18002f980`
- `0x18002fd30`
- `0x18002fe08`
- `0x18002febc`
- `0x1800302a8`
- `0x1800304c4`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18001ae1f`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18001ae1f`

## pseudocode

```c
ULONG __fastcall WPP_SF_(TRACEHANDLE a1, USHORT a2, const GUID *a3)
{
  return TraceMessage(a1, 0x2Bu, a3, a2, 0);
}

```

## disassembly

```asm
0x18001ae0c  sub     rsp, 38h
0x18001ae10  and     [rsp+38h+var_18], 0
0x18001ae16  movzx   r9d, dx; MessageNumber
0x18001ae1a  mov     edx, 2Bh ; '+'; MessageFlags
0x18001ae1f  call    cs:__imp_TraceMessage
0x18001ae26  nop     dword ptr [rax+rax+00h]
0x18001ae2b  add     rsp, 38h
0x18001ae2f  retn
```
