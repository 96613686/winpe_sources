# __security_check_cookie

- ea: `0x180012040`
- end: `0x18001205e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `34`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x180002a64`
- `0x180002eac`
- `0x18000353c`
- `0x1800037d8`
- `0x180003bf8`
- `0x180003f9c`
- `0x18000459c`
- `0x18000533c`
- `0x180005584`
- `0x180005f2c`
- `0x18000645c`
- `0x1800064f4`
- `0x180006590`
- `0x18000662c`
- `0x18000812c`
- `0x180008aec`
- `0x180009200`
- `0x18000a8f0`
- `0x18000ab34`
- `0x18000ac60`
- `0x18000ade8`
- `0x18000cf30`
- `0x18000d41c`
- `0x18000d700`
- `0x18000e14c`
- `0x18000fd04`
- `0x18000ff84`
- `0x1800107dc`
- `0x18001172c`
- `0x18001196c`
- `0x180011c10`
- `0x180011f88`

## callees

- `0x1800021a0`
- `0x180012040`

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
0x180012040  cmp     rcx, cs:__security_cookie
0x180012047  jnz     short ReportFailure
0x180012049  rol     rcx, 10h
0x18001204d  test    cx, 0FFFFh
0x180012052  jnz     short RestoreRcx
0x180012054  retn
0x180012055  ror     rcx, 10h
0x180012059  jmp     __report_gsfailure
```
