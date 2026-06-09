# __security_check_cookie

- ea: `0x140016560`
- end: `0x14001657e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `53`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400012b4`
- `0x1400043a0`
- `0x140004a60`
- `0x140006af0`
- `0x140007820`
- `0x14000c1f0`
- `0x14000d660`
- `0x14000e694`
- `0x14000e708`
- `0x14000fa8c`
- `0x14000fb5c`
- `0x140011028`
- `0x14001111c`
- `0x140012940`
- `0x140013168`
- `0x140013a7c`
- `0x140015ab8`
- `0x14001646c`
- `0x140028ee0`
- `0x14002a430`
- `0x14002d060`
- `0x14002e3c0`
- `0x14003021c`
- `0x14003108c`
- `0x1400317a0`
- `0x140031834`
- `0x140031adc`
- `0x140032114`
- `0x140032e60`
- `0x1400330b4`
- `0x14003330c`
- `0x140033520`
- `0x140033ef0`
- `0x14003652c`
- `0x140037780`
- `0x140038760`
- `0x1400394f0`
- `0x140039c84`
- `0x140039dc4`
- `0x14003c81c`
- `0x14003ceb8`
- `0x14003ec3c`
- `0x140040ea0`
- `0x14004245c`
- `0x140042fd4`
- `0x1400499e0`
- `0x14004fa60`
- `0x1400501d0`
- `0x140050ae0`
- `0x1400519f0`

## callees

- `0x14000dea0`
- `0x140016560`

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
0x140016560  cmp     rcx, cs:__security_cookie
0x140016567  jnz     short ReportFailure
0x140016569  rol     rcx, 10h
0x14001656d  test    cx, 0FFFFh
0x140016572  jnz     short RestoreRcx
0x140016574  retn
0x140016575  ror     rcx, 10h; StackCookie
0x140016579  jmp     __report_gsfailure
```
