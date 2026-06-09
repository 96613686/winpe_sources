# __security_check_cookie

- ea: `0x18000b100`
- end: `0x18000b11e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `13`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001200`
- `0x180001a80`
- `0x180002114`
- `0x180005d70`
- `0x18000627c`
- `0x18000688c`
- `0x180006c58`
- `0x1800088b8`
- `0x180009588`
- `0x180009784`
- `0x180009eac`
- `0x18000a2b0`
- `0x18000b044`

## callees

- `0x180003100`
- `0x18000b100`

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
0x18000b100  cmp     rcx, cs:__security_cookie
0x18000b107  jnz     short ReportFailure
0x18000b109  rol     rcx, 10h
0x18000b10d  test    cx, 0FFFFh
0x18000b112  jnz     short RestoreRcx
0x18000b114  retn
0x18000b115  ror     rcx, 10h
0x18000b119  jmp     __report_gsfailure
```
