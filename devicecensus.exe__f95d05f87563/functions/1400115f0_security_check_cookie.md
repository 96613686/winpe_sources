# __security_check_cookie

- ea: `0x1400115f0`
- end: `0x14001160e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `28`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x140001214`
- `0x1400025c0`
- `0x140002844`
- `0x140002c14`
- `0x140003610`
- `0x1400039d0`
- `0x140003bb4`
- `0x140003cd8`
- `0x1400042c0`
- `0x140004780`
- `0x140004dd4`
- `0x1400050a0`
- `0x140006460`
- `0x1400070e8`
- `0x140007184`
- `0x1400078bc`
- `0x14000b408`
- `0x14000ba04`
- `0x14000c460`
- `0x14000cb60`
- `0x14000cc48`
- `0x14000d190`
- `0x14000d704`
- `0x14000e380`
- `0x14000fb14`
- `0x1400109c4`
- `0x1400114d0`

## callees

- `0x140001bc0`
- `0x1400115f0`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
LABEL_4:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto LABEL_4;
  }
}

```

## disassembly

```asm
0x1400115f0  cmp     rcx, cs:__security_cookie
0x1400115f7  jnz     short loc_140011609
0x1400115f9  rol     rcx, 10h
0x1400115fd  test    cx, 0FFFFh
0x140011602  jnz     short loc_140011605
0x140011604  retn
0x140011605  ror     rcx, 10h
0x140011609  jmp     __report_gsfailure
```
