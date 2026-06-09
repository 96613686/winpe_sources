# __security_check_cookie

- ea: `0x18000ccc0`
- end: `0x18000ccde`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `34`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001134`
- `0x180001254`
- `0x18000134c`
- `0x1800013e0`
- `0x180002844`
- `0x180002b04`
- `0x1800031d4`
- `0x180003814`
- `0x180003bb0`
- `0x1800045a8`
- `0x1800057dc`
- `0x180006100`
- `0x180006300`
- `0x18000660c`
- `0x180006e40`
- `0x18000751c`
- `0x1800076ac`
- `0x180008a70`
- `0x180008dd0`
- `0x1800090e0`
- `0x1800093e0`
- `0x1800096c0`
- `0x18000a5f4`
- `0x18000ad90`
- `0x18000b064`
- `0x18000b2c0`
- `0x18000b570`
- `0x18000b81c`
- `0x18000ba60`
- `0x18000bce8`
- `0x18000be6c`
- `0x18000c47c`
- `0x18000c744`
- `0x18000cb9c`

## callees

- `0x180002010`
- `0x18000ccc0`

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
0x18000ccc0  cmp     rcx, cs:__security_cookie
0x18000ccc7  jnz     short ReportFailure
0x18000ccc9  rol     rcx, 10h
0x18000cccd  test    cx, 0FFFFh
0x18000ccd2  jnz     short RestoreRcx
0x18000ccd4  retn
0x18000ccd5  ror     rcx, 10h
0x18000ccd9  jmp     __report_gsfailure
```
