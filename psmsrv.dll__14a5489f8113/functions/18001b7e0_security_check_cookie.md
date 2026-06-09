# __security_check_cookie

- ea: `0x18001b7e0`
- end: `0x18001b7fe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `148`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000102c`
- `0x180001230`
- `0x18000171c`
- `0x1800017f8`
- `0x180002860`
- `0x1800032a0`
- `0x180003504`
- `0x1800037f4`
- `0x180003af0`
- `0x180003ec8`
- `0x1800043d8`
- `0x18000463c`
- `0x1800047b0`
- `0x180004d80`
- `0x180004f08`
- `0x1800051bc`
- `0x1800053a4`
- `0x1800056e8`
- `0x180005948`
- `0x180005b0c`
- `0x180005c74`
- `0x180005ed0`
- `0x1800060f0`
- `0x1800065a0`
- `0x180006750`
- `0x180006b7c`
- `0x180006d00`
- `0x180006e28`
- `0x1800070e4`
- `0x180007214`
- `0x18000772c`
- `0x1800078e0`
- `0x180007bb0`
- `0x180007d40`
- `0x180008360`
- `0x1800093d0`
- `0x180009630`
- `0x180009b40`
- `0x18000a750`
- `0x18000a8d0`
- `0x18000abf0`
- `0x18000b4d8`
- `0x18000b894`
- `0x18000bc20`
- `0x18000bdc0`
- `0x18000c7b0`
- `0x18000d16c`
- `0x18000d7e8`
- `0x18000dbd0`
- `0x18000defc`

## callees

- `0x18001b7e0`
- `0x18001bd90`

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
0x18001b7e0  cmp     rcx, cs:__security_cookie
0x18001b7e7  jnz     short ReportFailure
0x18001b7e9  rol     rcx, 10h
0x18001b7ed  test    cx, 0FFFFh
0x18001b7f2  jnz     short RestoreRcx
0x18001b7f4  retn
0x18001b7f5  ror     rcx, 10h; StackCookie
0x18001b7f9  jmp     __report_gsfailure
```
