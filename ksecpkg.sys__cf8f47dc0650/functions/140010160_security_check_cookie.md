# __security_check_cookie

- ea: `0x140010160`
- end: `0x14001017e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `71`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002160`
- `0x140003530`
- `0x1400037e0`
- `0x140003eb0`
- `0x140005170`
- `0x140006308`
- `0x140006ecc`
- `0x140007008`
- `0x140007150`
- `0x1400081a4`
- `0x1400088a4`
- `0x140008948`
- `0x1400089e0`
- `0x140008af4`
- `0x140009208`
- `0x14000a4ec`
- `0x14000a7e8`
- `0x14000acd4`
- `0x14000b920`
- `0x14000c63c`
- `0x14000c6fc`
- `0x14000ca84`
- `0x14000ce40`
- `0x14000d200`
- `0x14000d5d8`
- `0x14000e1a0`
- `0x14000e55c`
- `0x14000e66c`
- `0x14000e7b0`
- `0x14000ed60`
- `0x14000eef8`
- `0x14000f340`
- `0x14000f844`
- `0x14000f88c`
- `0x14000fbdc`
- `0x140020640`
- `0x140020a50`
- `0x140021804`
- `0x140021ea0`
- `0x1400223a4`
- `0x140022fe8`
- `0x140023240`
- `0x140023580`
- `0x140024008`
- `0x14002510c`
- `0x140026220`
- `0x140026f70`
- `0x1400276c0`
- `0x140028320`
- `0x1400283e0`

## callees

- `0x140006100`
- `0x140010160`

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
0x140010160  cmp     rcx, cs:__security_cookie
0x140010167  jnz     short ReportFailure
0x140010169  rol     rcx, 10h
0x14001016d  test    cx, 0FFFFh
0x140010172  jnz     short RestoreRcx
0x140010174  retn
0x140010175  ror     rcx, 10h; StackCookie
0x140010179  jmp     __report_gsfailure
```
