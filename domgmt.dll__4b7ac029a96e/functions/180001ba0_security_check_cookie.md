# __security_check_cookie

- ea: `0x180001ba0`
- end: `0x180001bbe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `32`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800012e8`
- `0x180002314`
- `0x180003568`
- `0x180003814`
- `0x180003db8`
- `0x180004188`
- `0x1800046f4`
- `0x180004a70`
- `0x1800063cc`
- `0x1800068b0`
- `0x180006af8`
- `0x180008334`
- `0x1800084c8`
- `0x1800085fc`
- `0x180008988`
- `0x180008c40`
- `0x180009774`
- `0x18000993c`
- `0x180009d90`
- `0x180009ec0`
- `0x180009f54`
- `0x18000a0b8`
- `0x18000a59c`
- `0x18000b6c0`
- `0x18000bbd0`
- `0x18000bd84`
- `0x18000bf1c`
- `0x18000c6b0`
- `0x18000c950`
- `0x18000cc90`
- `0x18000ce20`
- `0x18000cf60`

## callees

- `0x180001ba0`
- `0x180002540`

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
0x180001ba0  cmp     rcx, cs:__security_cookie
0x180001ba7  jnz     short ReportFailure
0x180001ba9  rol     rcx, 10h
0x180001bad  test    cx, 0FFFFh
0x180001bb2  jnz     short RestoreRcx
0x180001bb4  retn
0x180001bb5  ror     rcx, 10h; StackCookie
0x180001bb9  jmp     __report_gsfailure
```
