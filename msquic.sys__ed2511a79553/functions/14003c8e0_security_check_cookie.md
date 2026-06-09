# __security_check_cookie

- ea: `0x14003c8e0`
- end: `0x14003c8fe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `250`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400010b0`
- `0x140001860`
- `0x140001b00`
- `0x140001d6c`
- `0x140002840`
- `0x140002ca4`
- `0x140002e8c`
- `0x140003198`
- `0x140003738`
- `0x140003fac`
- `0x140004460`
- `0x140004730`
- `0x1400049b0`
- `0x1400051c0`
- `0x14000524c`
- `0x140005aa4`
- `0x140006a2c`
- `0x1400078c8`
- `0x1400079e4`
- `0x1400087bc`
- `0x140008944`
- `0x140008af8`
- `0x140008bb0`
- `0x140008f50`
- `0x140009438`
- `0x140009534`
- `0x1400098e8`
- `0x1400099b4`
- `0x14000a120`
- `0x14000a2b0`
- `0x14000a6f0`
- `0x14000acfc`
- `0x14000b098`
- `0x14000b1f8`
- `0x14000b27c`
- `0x14000b32c`
- `0x14000b60c`
- `0x14000bad0`
- `0x14000ca70`
- `0x14000d230`
- `0x14000d428`
- `0x14000d490`
- `0x14000d7a0`
- `0x14000da60`
- `0x14000db70`
- `0x14000edc0`
- `0x14000f400`
- `0x14000fdb0`
- `0x140010440`
- `0x1400108c0`

## callees

- `0x1400276f0`
- `0x14003c8e0`

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
0x14003c8e0  cmp     rcx, cs:__security_cookie
0x14003c8e7  jnz     short ReportFailure
0x14003c8e9  rol     rcx, 10h
0x14003c8ed  test    cx, 0FFFFh
0x14003c8f2  jnz     short RestoreRcx
0x14003c8f4  retn
0x14003c8f5  ror     rcx, 10h; StackCookie
0x14003c8f9  jmp     __report_gsfailure
```
