# __security_check_cookie

- ea: `0x140003690`
- end: `0x1400036ae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001990`
- `0x14000360c`
- `0x14000ab60`
- `0x14000d2c4`

## callees

- `0x140001010`
- `0x140003690`

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
0x140003690  cmp     rcx, cs:__security_cookie
0x140003697  jnz     short ReportFailure
0x140003699  rol     rcx, 10h
0x14000369d  test    cx, 0FFFFh
0x1400036a2  jnz     short RestoreRcx
0x1400036a4  retn
0x1400036a5  ror     rcx, 10h; StackCookie
0x1400036a9  jmp     __report_gsfailure
```
