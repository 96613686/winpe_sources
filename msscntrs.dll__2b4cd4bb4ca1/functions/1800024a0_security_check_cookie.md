# __security_check_cookie

- ea: `0x1800024a0`
- end: `0x1800024be`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `47`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001100`
- `0x1800013b4`
- `0x1800016ac`
- `0x18000187c`
- `0x180003ce8`
- `0x180003f94`
- `0x1800050b8`
- `0x180005488`
- `0x180005880`
- `0x1800063c4`
- `0x180006740`
- `0x1800077f4`
- `0x180007900`
- `0x18000830c`
- `0x180009b0c`
- `0x18000a8a0`
- `0x18000a9c8`
- `0x18000ac98`
- `0x18000bd2c`
- `0x18000c690`
- `0x18000c84c`
- `0x18000da9c`
- `0x18000dd2c`
- `0x18000df84`
- `0x18000e1b8`
- `0x18000e624`
- `0x18000eae8`
- `0x18000ec38`
- `0x18000edc8`
- `0x18000efac`
- `0x18000ff04`
- `0x18000ffec`
- `0x180010314`
- `0x18001067c`
- `0x180010a34`
- `0x180010db0`
- `0x1800111b0`
- `0x180011500`
- `0x18001353c`
- `0x180013ad8`
- `0x180013bf4`
- `0x1800140d8`
- `0x1800142d8`
- `0x180014394`
- `0x180014d9c`
- `0x180015570`

## callees

- `0x1800024a0`
- `0x180002ca0`

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
0x1800024a0  cmp     rcx, cs:__security_cookie
0x1800024a7  jnz     short ReportFailure
0x1800024a9  rol     rcx, 10h
0x1800024ad  test    cx, 0FFFFh
0x1800024b2  jnz     short RestoreRcx
0x1800024b4  retn
0x1800024b5  ror     rcx, 10h; StackCookie
0x1800024b9  jmp     __report_gsfailure
```
