# __security_check_cookie

- ea: `0x180002b10`
- end: `0x180002b2e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `41`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800012b8`
- `0x18000156c`
- `0x180001864`
- `0x180001a88`
- `0x180001ad0`
- `0x180001de4`
- `0x180001e74`
- `0x180001f70`
- `0x180002034`
- `0x1800020a4`
- `0x180002180`
- `0x1800022a0`
- `0x180002398`
- `0x180003d28`
- `0x180003fbc`
- `0x180004628`
- `0x180004808`
- `0x180004ba4`
- `0x180004fa0`
- `0x1800066c8`
- `0x180006cc0`
- `0x180009690`
- `0x1800098d0`
- `0x18000af90`
- `0x18000b804`
- `0x18000de50`
- `0x18000ec88`
- `0x180010acc`
- `0x180010bfc`
- `0x180011290`
- `0x1800114f0`
- `0x180011b30`
- `0x180012790`
- `0x1800129c0`
- `0x180012c00`
- `0x180012f10`
- `0x180015cd0`
- `0x180015e98`
- `0x180017764`
- `0x180018620`

## callees

- `0x180002b10`
- `0x180003150`

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
0x180002b10  cmp     rcx, cs:__security_cookie
0x180002b17  jnz     short ReportFailure
0x180002b19  rol     rcx, 10h
0x180002b1d  test    cx, 0FFFFh
0x180002b22  jnz     short RestoreRcx
0x180002b24  retn
0x180002b25  ror     rcx, 10h; StackCookie
0x180002b29  jmp     __report_gsfailure
```
