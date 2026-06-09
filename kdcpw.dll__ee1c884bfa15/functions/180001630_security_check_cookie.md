# __security_check_cookie

- ea: `0x180001630`
- end: `0x18000164e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `15`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002d7c`
- `0x180003018`
- `0x1800039e4`
- `0x180003d88`
- `0x180004158`
- `0x180004f34`
- `0x1800052ac`
- `0x180005978`
- `0x180006744`
- `0x180006850`
- `0x180007248`
- `0x1800085f8`
- `0x180009014`
- `0x18000954c`
- `0x18000ca10`

## callees

- `0x180001630`
- `0x180001bc0`

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
0x180001630  cmp     rcx, cs:__security_cookie
0x180001637  jnz     short ReportFailure
0x180001639  rol     rcx, 10h
0x18000163d  test    cx, 0FFFFh
0x180001642  jnz     short RestoreRcx
0x180001644  retn
0x180001645  ror     rcx, 10h; StackCookie
0x180001649  jmp     __report_gsfailure
```
