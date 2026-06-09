# __security_check_cookie

- ea: `0x18000dd10`
- end: `0x18000dd2e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `21`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001d40`
- `0x180001e8c`
- `0x1800028fc`
- `0x180003150`
- `0x1800032f8`
- `0x1800037c0`
- `0x18000466c`
- `0x180004a38`
- `0x180004b88`
- `0x180004d18`
- `0x180004efc`
- `0x180005928`
- `0x180005b1c`
- `0x180005e3c`
- `0x180008d7c`
- `0x18000be1c`
- `0x18000c580`
- `0x18000cbb0`
- `0x18000cdac`
- `0x18000d94c`
- `0x18000d990`

## callees

- `0x180001790`
- `0x18000dd10`

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
0x18000dd10  cmp     rcx, cs:__security_cookie
0x18000dd17  jnz     short ReportFailure
0x18000dd19  rol     rcx, 10h
0x18000dd1d  test    cx, 0FFFFh
0x18000dd22  jnz     short RestoreRcx
0x18000dd24  retn
0x18000dd25  ror     rcx, 10h
0x18000dd29  jmp     __report_gsfailure
```
