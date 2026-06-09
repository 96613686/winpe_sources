# __security_check_cookie

- ea: `0x14003e430`
- end: `0x14003e44e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `145`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001130`
- `0x1400024b0`
- `0x140002844`
- `0x140002d30`
- `0x140004300`
- `0x140004ed0`
- `0x1400050a0`
- `0x140005190`
- `0x140005560`
- `0x140005c30`
- `0x1400061e0`
- `0x140006300`
- `0x1400066cc`
- `0x140006f60`
- `0x140007000`
- `0x140007230`
- `0x14000740c`
- `0x1400074b8`
- `0x1400077ac`
- `0x140008024`
- `0x140008360`
- `0x1400084b0`
- `0x14000cd60`
- `0x14000d3e0`
- `0x14000de10`
- `0x140010400`
- `0x140011ba0`
- `0x140013240`
- `0x140014418`
- `0x140014860`
- `0x140015890`
- `0x140015b00`
- `0x140015c50`
- `0x140016350`
- `0x140017df8`
- `0x1400181ec`
- `0x140018424`
- `0x1400186b0`
- `0x140018f70`
- `0x140019ce4`
- `0x140019de0`
- `0x14001c9e0`
- `0x14001ccb0`
- `0x14001e2f0`
- `0x14001e86c`
- `0x14001ecc0`
- `0x14001f154`
- `0x140020624`
- `0x140021a20`
- `0x140021c78`

## callees

- `0x1400219e0`
- `0x14003e430`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
ReportFailure:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto ReportFailure;
  }
}

```

## disassembly

```asm
0x14003e430  cmp     rcx, cs:__security_cookie
0x14003e437  jnz     short ReportFailure
0x14003e439  rol     rcx, 10h
0x14003e43d  test    cx, 0FFFFh
0x14003e442  jnz     short RestoreRcx
0x14003e444  retn
0x14003e445  ror     rcx, 10h; StackCookie
0x14003e449  jmp     __report_gsfailure
```
