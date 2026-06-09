# __security_check_cookie

- ea: `0x180018950`
- end: `0x18001896e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `22`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x18000142c`
- `0x1800066e0`
- `0x18000a3c8`
- `0x18000a798`
- `0x18000a8e8`
- `0x18000f9b0`
- `0x180011c6c`
- `0x180011d60`
- `0x180012668`
- `0x1800127d0`
- `0x180012998`
- `0x180013294`
- `0x1800135ac`
- `0x180014a14`
- `0x180014d94`
- `0x180015fcc`
- `0x180016a10`
- `0x180016c18`
- `0x180017010`
- `0x180017f88`
- `0x1800187c4`

## callees

- `0x18000c1e0`
- `0x180018950`

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
0x180018950  cmp     rcx, cs:__security_cookie
0x180018957  jnz     short ReportFailure
0x180018959  rol     rcx, 10h
0x18001895d  test    cx, 0FFFFh
0x180018962  jnz     short RestoreRcx
0x180018964  retn
0x180018965  ror     rcx, 10h
0x180018969  jmp     __report_gsfailure
```
