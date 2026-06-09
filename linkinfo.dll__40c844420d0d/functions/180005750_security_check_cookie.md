# __security_check_cookie

- ea: `0x180005750`
- end: `0x18000576e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `28`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800014c0`
- `0x180001580`
- `0x180001840`
- `0x1800019e0`
- `0x180001e30`
- `0x180001f10`
- `0x1800023f0`
- `0x180002500`
- `0x1800028c0`
- `0x180002b00`
- `0x1800030d0`
- `0x1800031f0`
- `0x1800033c0`
- `0x1800034b0`
- `0x1800042d0`
- `0x1800043e4`
- `0x1800044f0`
- `0x180004760`
- `0x180004840`
- `0x1800048ec`
- `0x1800049dc`
- `0x180004b50`
- `0x180004eb0`
- `0x180005110`
- `0x180005240`
- `0x1800054e0`
- `0x1800055e0`
- `0x1800056ac`

## callees

- `0x180003c30`
- `0x180005750`

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
0x180005750  cmp     rcx, cs:__security_cookie
0x180005757  jnz     short ReportFailure
0x180005759  rol     rcx, 10h
0x18000575d  test    cx, 0FFFFh
0x180005762  jnz     short RestoreRcx
0x180005764  retn
0x180005765  ror     rcx, 10h
0x180005769  jmp     __report_gsfailure
```
