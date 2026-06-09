# __security_check_cookie

- ea: `0x180011eb0`
- end: `0x180011ece`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `18`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001310`
- `0x1800036d0`
- `0x180003b90`
- `0x180004bd0`
- `0x180006600`
- `0x180007ad0`
- `0x18000b8dc`
- `0x18000ba88`
- `0x18000c7e0`
- `0x18000d0ec`
- `0x18000da5c`
- `0x18000dd38`
- `0x18000e034`
- `0x18000e494`
- `0x18000edb4`
- `0x18000f154`
- `0x18001068c`
- `0x180011d98`

## callees

- `0x18000a510`
- `0x180011eb0`

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
0x180011eb0  cmp     rcx, cs:__security_cookie
0x180011eb7  jnz     short ReportFailure
0x180011eb9  rol     rcx, 10h
0x180011ebd  test    cx, 0FFFFh
0x180011ec2  jnz     short RestoreRcx
0x180011ec4  retn
0x180011ec5  ror     rcx, 10h
0x180011ec9  jmp     __report_gsfailure
```
