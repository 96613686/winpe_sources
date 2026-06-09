# __security_check_cookie

- ea: `0x18000eca0`
- end: `0x18000ecbe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `33`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800024d0`
- `0x180002840`
- `0x180002b50`
- `0x180002c8c`
- `0x180003030`
- `0x180003d48`
- `0x180004160`
- `0x180005020`
- `0x180005394`
- `0x180005b34`
- `0x180005e90`
- `0x180006730`
- `0x180006870`
- `0x180007250`
- `0x18000744c`
- `0x180007688`
- `0x1800078d0`
- `0x180007ff0`
- `0x180008720`
- `0x18000a7ac`
- `0x18000ab80`
- `0x18000b120`
- `0x18000bc18`
- `0x18000bf7c`
- `0x18000c170`
- `0x18000c634`
- `0x18000cb70`
- `0x18000df20`
- `0x18000e0d0`
- `0x18000e300`
- `0x18000e600`
- `0x18000eaec`
- `0x18000ebe8`

## callees

- `0x1800015a0`
- `0x18000eca0`

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
0x18000eca0  cmp     rcx, cs:__security_cookie
0x18000eca7  jnz     short ReportFailure
0x18000eca9  rol     rcx, 10h
0x18000ecad  test    cx, 0FFFFh
0x18000ecb2  jnz     short RestoreRcx
0x18000ecb4  retn
0x18000ecb5  ror     rcx, 10h
0x18000ecb9  jmp     __report_gsfailure
```
