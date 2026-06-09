# __security_check_cookie

- ea: `0x1800096b0`
- end: `0x1800096ce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `12`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003158`
- `0x180006418`
- `0x180006520`
- `0x180006a80`
- `0x180006b68`
- `0x1800074d4`
- `0x180008310`
- `0x1800083e0`
- `0x1800086b8`
- `0x180008c30`
- `0x180009160`
- `0x1800095a4`

## callees

- `0x180001ae0`
- `0x1800096b0`

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
0x1800096b0  cmp     rcx, cs:__security_cookie
0x1800096b7  jnz     short ReportFailure
0x1800096b9  rol     rcx, 10h
0x1800096bd  test    cx, 0FFFFh
0x1800096c2  jnz     short RestoreRcx
0x1800096c4  retn
0x1800096c5  ror     rcx, 10h
0x1800096c9  jmp     __report_gsfailure
```
