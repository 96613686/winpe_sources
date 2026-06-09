# __security_check_cookie

- ea: `0x180011ba0`
- end: `0x180011bbe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `54`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000222c`
- `0x1800024e8`
- `0x180002930`
- `0x180003344`
- `0x1800036d4`
- `0x180003b40`
- `0x180004604`
- `0x180004720`
- `0x180005850`
- `0x180005c10`
- `0x180005d70`
- `0x1800060e0`
- `0x180006410`
- `0x1800066c0`
- `0x180007330`
- `0x180007bc0`
- `0x180007fd0`
- `0x180008420`
- `0x180008548`
- `0x180008730`
- `0x180009660`
- `0x180009948`
- `0x18000adf4`
- `0x18000b134`
- `0x18000b9b8`
- `0x18000be24`
- `0x18000ca9c`
- `0x18000cbe0`
- `0x18000cc98`
- `0x18000cf74`
- `0x18000d5d8`
- `0x18000d884`
- `0x18000dc1c`
- `0x18000dd70`
- `0x18000df74`
- `0x18000e1f0`
- `0x18000e320`
- `0x18000e4f0`
- `0x18000e5f4`
- `0x18000e87c`
- `0x18000e984`
- `0x18000ebc4`
- `0x18000eccc`
- `0x18000efac`
- `0x18000f278`
- `0x18000f470`
- `0x18000f64c`
- `0x18000f7b0`
- `0x18000f9f0`
- `0x18000fc20`

## callees

- `0x180001520`
- `0x180011ba0`

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
0x180011ba0  cmp     rcx, cs:__security_cookie
0x180011ba7  jnz     short ReportFailure
0x180011ba9  rol     rcx, 10h
0x180011bad  test    cx, 0FFFFh
0x180011bb2  jnz     short RestoreRcx
0x180011bb4  retn
0x180011bb5  ror     rcx, 10h
0x180011bb9  jmp     __report_gsfailure
```
