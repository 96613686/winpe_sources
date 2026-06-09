# __security_check_cookie

- ea: `0x18000a5b0`
- end: `0x18000a5ce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `18`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002160`
- `0x180002fe8`
- `0x1800038f0`
- `0x180004240`
- `0x18000473c`
- `0x180004be8`
- `0x180004ed4`
- `0x180005130`
- `0x180005dbc`
- `0x180006374`
- `0x180006510`
- `0x180006588`
- `0x180006ad0`
- `0x1800074d4`
- `0x180007fc0`
- `0x18000879c`
- `0x180009ac0`
- `0x18000a428`

## callees

- `0x180001a30`
- `0x18000a5b0`

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
0x18000a5b0  cmp     rcx, cs:__security_cookie
0x18000a5b7  jnz     short ReportFailure
0x18000a5b9  rol     rcx, 10h
0x18000a5bd  test    cx, 0FFFFh
0x18000a5c2  jnz     short RestoreRcx
0x18000a5c4  retn
0x18000a5c5  ror     rcx, 10h
0x18000a5c9  jmp     __report_gsfailure
```
