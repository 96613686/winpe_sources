# __security_check_cookie

- ea: `0x180001ce0`
- end: `0x180001cfe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `28`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800010e0`
- `0x180001394`
- `0x180004c28`
- `0x180005a14`
- `0x180006014`
- `0x1800064e4`
- `0x180007c10`
- `0x180008a68`
- `0x180008d44`
- `0x180008eb8`
- `0x18000920c`
- `0x180009370`
- `0x180009800`
- `0x180009ae4`
- `0x180009c18`
- `0x18000a26c`
- `0x18000a89c`
- `0x18000a9a4`
- `0x18000aaac`
- `0x18000b088`
- `0x18000b324`
- `0x18000b59c`
- `0x18000b940`
- `0x18000bed4`
- `0x18000c24c`
- `0x18000d36c`
- `0x18000d76c`

## callees

- `0x180001ce0`
- `0x180002290`

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
0x180001ce0  cmp     rcx, cs:__security_cookie
0x180001ce7  jnz     short ReportFailure
0x180001ce9  rol     rcx, 10h
0x180001ced  test    cx, 0FFFFh
0x180001cf2  jnz     short RestoreRcx
0x180001cf4  retn
0x180001cf5  ror     rcx, 10h; StackCookie
0x180001cf9  jmp     __report_gsfailure
```
