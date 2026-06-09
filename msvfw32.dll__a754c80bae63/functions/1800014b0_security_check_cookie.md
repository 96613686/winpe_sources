# __security_check_cookie

- ea: `0x1800014b0`
- end: `0x1800014ce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `63`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001e9c`
- `0x180001fd8`
- `0x180002e90`
- `0x1800031d0`
- `0x1800033e0`
- `0x1800035d0`
- `0x180003960`
- `0x180003b1c`
- `0x180003bf0`
- `0x180003ca0`
- `0x180004088`
- `0x1800043b0`
- `0x1800047f0`
- `0x1800065e0`
- `0x1800068bc`
- `0x180006cf0`
- `0x180006e70`
- `0x1800070f0`
- `0x1800074a0`
- `0x1800076c4`
- `0x18000824c`
- `0x180009bb0`
- `0x18000ab84`
- `0x18000b2ac`
- `0x18000b928`
- `0x18000bc24`
- `0x18000be48`
- `0x18000c300`
- `0x18000d080`
- `0x18000d4e0`
- `0x18000df3c`
- `0x18000eb40`
- `0x18000ed20`
- `0x18000f25c`
- `0x18000f41c`
- `0x18000f704`
- `0x18000f9a8`
- `0x18000fe2c`
- `0x180010824`
- `0x180010884`
- `0x180010998`
- `0x180010aa4`
- `0x180010c08`
- `0x180010cc0`
- `0x1800127bc`
- `0x180012934`
- `0x1800129a0`
- `0x180012ac4`
- `0x18001306c`
- `0x1800132b8`

## callees

- `0x1800014b0`
- `0x1800014e0`

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
0x1800014b0  cmp     rcx, cs:__security_cookie
0x1800014b7  jnz     short ReportFailure
0x1800014b9  rol     rcx, 10h
0x1800014bd  test    cx, 0FFFFh
0x1800014c2  jnz     short RestoreRcx
0x1800014c4  retn
0x1800014c5  ror     rcx, 10h; StackCookie
0x1800014c9  jmp     __report_gsfailure
```
