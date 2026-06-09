# __security_check_cookie

- ea: `0x1800191f0`
- end: `0x18001920e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `50`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001214`
- `0x18000312c`
- `0x180003388`
- `0x18000354c`
- `0x1800039c8`
- `0x180004358`
- `0x180004a2c`
- `0x180004d68`
- `0x1800055f4`
- `0x180005ef4`
- `0x180006664`
- `0x180006934`
- `0x180007170`
- `0x180007504`
- `0x180007c90`
- `0x180007e34`
- `0x180008250`
- `0x180008628`
- `0x180008c38`
- `0x180009200`
- `0x180009650`
- `0x1800096e0`
- `0x180009a20`
- `0x180009c00`
- `0x18000a208`
- `0x18000aaf4`
- `0x18000ae60`
- `0x18000cfa4`
- `0x18000d788`
- `0x18000d824`
- `0x18000d910`
- `0x18000eb90`
- `0x18000f6e4`
- `0x18000f7cc`
- `0x18000fd14`
- `0x180010288`
- `0x180010f04`
- `0x180012fa0`
- `0x180013814`
- `0x180014bfc`
- `0x180015020`
- `0x1800154e0`
- `0x180016590`
- `0x180016880`
- `0x1800174a4`
- `0x1800187d0`
- `0x1800189a0`
- `0x180018cc4`
- `0x1800190b8`

## callees

- `0x180002390`
- `0x1800191f0`

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
0x1800191f0  cmp     rcx, cs:__security_cookie
0x1800191f7  jnz     short ReportFailure
0x1800191f9  rol     rcx, 10h
0x1800191fd  test    cx, 0FFFFh
0x180019202  jnz     short RestoreRcx
0x180019204  retn
0x180019205  ror     rcx, 10h
0x180019209  jmp     __report_gsfailure
```
