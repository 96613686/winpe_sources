# __security_check_cookie

- ea: `0x140005bb0`
- end: `0x140005bce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `36`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002ce8`
- `0x140003408`
- `0x140005abc`
- `0x1400140b4`
- `0x1400143e8`
- `0x140014474`
- `0x140014970`
- `0x140015078`
- `0x140015388`
- `0x1400161c0`
- `0x140016238`
- `0x1400162cc`
- `0x140016c00`
- `0x140016d44`
- `0x140016e78`
- `0x140017aac`
- `0x140017c04`
- `0x1400181a4`
- `0x1400184e0`
- `0x1400185bc`
- `0x140018630`
- `0x140018760`
- `0x140018f20`
- `0x140019730`
- `0x14001af3c`
- `0x14001c3d0`
- `0x14001e720`
- `0x14001ea10`
- `0x140020400`
- `0x140021e40`
- `0x140023058`
- `0x140023cc4`
- `0x140024790`
- `0x140028714`
- `0x1400291a8`
- `0x140029574`

## callees

- `0x140002500`
- `0x140005bb0`

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
0x140005bb0  cmp     rcx, cs:__security_cookie
0x140005bb7  jnz     short ReportFailure
0x140005bb9  rol     rcx, 10h
0x140005bbd  test    cx, 0FFFFh
0x140005bc2  jnz     short RestoreRcx
0x140005bc4  retn
0x140005bc5  ror     rcx, 10h; StackCookie
0x140005bc9  jmp     __report_gsfailure
```
