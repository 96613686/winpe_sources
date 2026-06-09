# __security_check_cookie

- ea: `0x18005b680`
- end: `0x18005b69e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `63`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001048`
- `0x180001184`
- `0x1800015a8`
- `0x1800019b0`
- `0x180001f00`
- `0x180003650`
- `0x180004bb0`
- `0x180004d40`
- `0x180007390`
- `0x180031c1c`
- `0x180032000`
- `0x180032f74`
- `0x180033098`
- `0x18003391c`
- `0x1800344d8`
- `0x18005b4bc`
- `0x1800e6010`
- `0x1800e7aa0`
- `0x1800e8d80`
- `0x1800e8f70`
- `0x1800e90c0`
- `0x1800e9188`
- `0x1800e95a8`
- `0x1800e9730`
- `0x1800e9950`
- `0x1800ea350`
- `0x1800ea880`
- `0x1800eaa0c`
- `0x1800eb000`
- `0x1800ebb90`
- `0x1800ebe70`
- `0x1800ec02c`
- `0x1800ec3e8`
- `0x1800ec89c`
- `0x1800ecc70`
- `0x1800ed7d0`
- `0x1800ed890`
- `0x1800eda90`
- `0x1800edc90`
- `0x1800edf50`
- `0x1800ee1c0`
- `0x1800ee3e0`
- `0x1800ee610`
- `0x1800ee9e0`
- `0x1800eebf0`
- `0x1800eefb0`
- `0x1800ef200`
- `0x1800ef4d0`
- `0x1800ef6f0`
- `0x1800ef9c0`

## callees

- `0x180033050`
- `0x18005b680`

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
0x18005b680  cmp     rcx, cs:__security_cookie
0x18005b687  jnz     short ReportFailure
0x18005b689  rol     rcx, 10h
0x18005b68d  test    cx, 0FFFFh
0x18005b692  jnz     short RestoreRcx
0x18005b694  retn
0x18005b695  ror     rcx, 10h; StackCookie
0x18005b699  jmp     __report_gsfailure
```
