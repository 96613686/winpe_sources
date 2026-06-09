# __security_check_cookie

- ea: `0x140001370`
- end: `0x14000138e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `20`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000127c`
- `0x140008224`
- `0x1400082ec`
- `0x1400083e4`
- `0x14000868c`
- `0x140008840`
- `0x14000ad30`
- `0x14000b080`
- `0x14000b280`
- `0x14000b820`
- `0x14000ba08`
- `0x14000d8fc`
- `0x14000d98c`
- `0x14000e088`
- `0x14000e6f8`
- `0x14000eb28`
- `0x14000ff68`
- `0x1400109dc`
- `0x140012078`
- `0x1400124bc`

## callees

- `0x140001090`
- `0x140001370`

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
0x140001370  cmp     rcx, cs:__security_cookie
0x140001377  jnz     short ReportFailure
0x140001379  rol     rcx, 10h
0x14000137d  test    cx, 0FFFFh
0x140001382  jnz     short RestoreRcx
0x140001384  retn
0x140001385  ror     rcx, 10h; StackCookie
0x140001389  jmp     __report_gsfailure
```
