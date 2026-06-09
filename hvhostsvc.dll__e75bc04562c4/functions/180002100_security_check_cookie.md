# __security_check_cookie

- ea: `0x180002100`
- end: `0x18000211e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `17`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800013a0`
- `0x180001a80`
- `0x18000317c`
- `0x180003410`
- `0x180003a38`
- `0x180003c14`
- `0x180003fb4`
- `0x180004368`
- `0x180004928`
- `0x1800049e0`
- `0x180005cc8`
- `0x180006190`
- `0x180006da8`
- `0x1800075ec`
- `0x180007b7c`
- `0x1800084f4`
- `0x180008ec8`

## callees

- `0x180002100`
- `0x1800026f0`

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
0x180002100  cmp     rcx, cs:__security_cookie
0x180002107  jnz     short ReportFailure
0x180002109  rol     rcx, 10h
0x18000210d  test    cx, 0FFFFh
0x180002112  jnz     short RestoreRcx
0x180002114  retn
0x180002115  ror     rcx, 10h; StackCookie
0x180002119  jmp     __report_gsfailure
```
