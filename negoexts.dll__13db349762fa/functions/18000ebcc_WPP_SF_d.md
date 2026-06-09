# WPP_SF_d

- ea: `0x18000ebcc`
- end: `0x18000ec03`
- name: `WPP_SF_d`
- size: `55`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `29`
- callee_count: `0`
- tags: ``

## callers

- `0x180001414`
- `0x1800038e0`
- `0x180003a10`
- `0x180004404`
- `0x180005bc0`
- `0x1800063e4`
- `0x1800070d0`
- `0x180008e60`
- `0x18000a020`
- `0x18000a160`
- `0x18000a29c`
- `0x18000bf1c`
- `0x18000c5f0`
- `0x18000d234`
- `0x18000d388`
- `0x180014150`
- `0x180017f00`
- `0x180019200`
- `0x1800194d0`
- `0x180019560`
- `0x180019600`
- `0x1800196a0`
- `0x180019730`
- `0x180019840`
- `0x180019950`
- `0x180019a70`
- `0x180019b80`
- `0x180019bf0`
- `0x18001a3b4`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000ebf8`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000ebf8`

## pseudocode

```c
ULONG __fastcall WPP_SF_d(TRACEHANDLE a1, USHORT a2, const GUID *a3, int a4)
{
  int v5; // [rsp+68h] [rbp+20h] BYREF

  v5 = a4;
  return TraceMessage(a1, 0x2Bu, a3, a2, &v5, 4, 0);
}

```

## disassembly

```asm
0x18000ebcc  mov     r11, rsp
0x18000ebcf  mov     [r11+20h], r9d
0x18000ebd3  sub     rsp, 48h
0x18000ebd7  mov     qword ptr [r11-18h], 0
0x18000ebdf  lea     rax, [r11+20h]
0x18000ebe3  movzx   r9d, dx; MessageNumber
0x18000ebe7  mov     edx, 2Bh ; '+'; MessageFlags
0x18000ebec  mov     qword ptr [r11-20h], 4
0x18000ebf4  mov     [r11-28h], rax
0x18000ebf8  call    cs:__imp_TraceMessage
0x18000ebfe  add     rsp, 48h
0x18000ec02  retn
```
