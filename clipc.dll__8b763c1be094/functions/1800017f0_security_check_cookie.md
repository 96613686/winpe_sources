# __security_check_cookie

- ea: `0x1800017f0`
- end: `0x18000180e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `24`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001140`
- `0x180002c8c`
- `0x180002f78`
- `0x1800031ac`
- `0x180003580`
- `0x180006390`
- `0x180006ad0`
- `0x18001003c`
- `0x18001aff4`
- `0x18001b1e8`
- `0x18001b2e8`
- `0x18001dfd0`
- `0x18001efa0`
- `0x180021e30`
- `0x1800228b0`
- `0x180022df0`
- `0x180023820`
- `0x180023b08`
- `0x180023e40`
- `0x180024234`
- `0x180024960`
- `0x180024c54`
- `0x180028054`

## callees

- `0x1800017f0`
- `0x180001dd0`

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
0x1800017f0  cmp     rcx, cs:__security_cookie
0x1800017f7  jnz     short ReportFailure
0x1800017f9  rol     rcx, 10h
0x1800017fd  test    cx, 0FFFFh
0x180001802  jnz     short RestoreRcx
0x180001804  retn
0x180001805  ror     rcx, 10h; StackCookie
0x180001809  jmp     __report_gsfailure
```
