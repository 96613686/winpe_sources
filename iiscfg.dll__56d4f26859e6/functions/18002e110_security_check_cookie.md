# __security_check_cookie

- ea: `0x18002e110`
- end: `0x18002e12e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `54`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003370`
- `0x180004ce0`
- `0x180004f40`
- `0x180005cb8`
- `0x180005fdc`
- `0x180006750`
- `0x18000a9b4`
- `0x18000c0b0`
- `0x18000cbcc`
- `0x18000d110`
- `0x18000ecb8`
- `0x1800114c0`
- `0x180011b38`
- `0x180012224`
- `0x1800125d0`
- `0x180012b68`
- `0x180012fbc`
- `0x180013140`
- `0x180013428`
- `0x1800139c0`
- `0x180013d80`
- `0x1800147c0`
- `0x180015f34`
- `0x180017114`
- `0x180017b70`
- `0x180019128`
- `0x180019554`
- `0x1800199c8`
- `0x18001a2e0`
- `0x18001a444`
- `0x18001a914`
- `0x18001aac4`
- `0x18001b014`
- `0x18001b188`
- `0x18001b354`
- `0x18001b628`
- `0x18001b82c`
- `0x18001c86c`
- `0x18001d2a0`
- `0x18001d604`
- `0x18001da08`
- `0x18001dd08`
- `0x1800234ac`
- `0x180023e00`
- `0x18002aad0`
- `0x18002b52c`
- `0x18002bc00`
- `0x18002c12c`
- `0x18002c604`
- `0x18002ccc8`

## callees

- `0x1800019d0`
- `0x18002e110`

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
0x18002e110  cmp     rcx, cs:__security_cookie
0x18002e117  jnz     short ReportFailure
0x18002e119  rol     rcx, 10h
0x18002e11d  test    cx, 0FFFFh
0x18002e122  jnz     short RestoreRcx
0x18002e124  retn
0x18002e125  ror     rcx, 10h
0x18002e129  jmp     __report_gsfailure
```
