# __security_check_cookie

- ea: `0x140005f70`
- end: `0x140005f8e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `22`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000141c`
- `0x14000193c`
- `0x140001bd8`
- `0x1400032fc`
- `0x140004314`
- `0x140005520`
- `0x1400057c4`
- `0x140005a70`
- `0x140005dac`
- `0x140011760`
- `0x140013908`
- `0x140013a00`
- `0x140013cbc`
- `0x1400140bc`
- `0x1400170a8`
- `0x140025f20`
- `0x140028004`
- `0x14002856c`
- `0x1400286dc`
- `0x140029160`
- `0x14002a078`
- `0x14002aafc`

## callees

- `0x140002410`
- `0x140005f70`

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
0x140005f70  cmp     rcx, cs:__security_cookie
0x140005f77  jnz     short ReportFailure
0x140005f79  rol     rcx, 10h
0x140005f7d  test    cx, 0FFFFh
0x140005f82  jnz     short RestoreRcx
0x140005f84  retn
0x140005f85  ror     rcx, 10h; StackCookie
0x140005f89  jmp     __report_gsfailure
```
