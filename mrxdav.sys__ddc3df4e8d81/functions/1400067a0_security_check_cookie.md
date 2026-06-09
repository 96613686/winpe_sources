# __security_check_cookie

- ea: `0x1400067a0`
- end: `0x1400067be`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000670c`
- `0x14000f9d4`
- `0x140018188`
- `0x14002000c`
- `0x1400220c0`
- `0x1400241b0`

## callees

- `0x140001010`
- `0x1400067a0`

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
0x1400067a0  cmp     rcx, cs:__security_cookie
0x1400067a7  jnz     short ReportFailure
0x1400067a9  rol     rcx, 10h
0x1400067ad  test    cx, 0FFFFh
0x1400067b2  jnz     short RestoreRcx
0x1400067b4  retn
0x1400067b5  ror     rcx, 10h; StackCookie
0x1400067b9  jmp     __report_gsfailure
```
