# __security_check_cookie

- ea: `0x1800181e0`
- end: `0x1800181fe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `37`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002060`
- `0x18000218c`
- `0x180002900`
- `0x180002ba0`
- `0x180002cc0`
- `0x18000c070`
- `0x18000c1a4`
- `0x18000c2a0`
- `0x18000c470`
- `0x18000ce90`
- `0x18000e0bc`
- `0x18000e910`
- `0x18000eb5c`
- `0x18000f024`
- `0x180010020`
- `0x18001098c`
- `0x180010dc8`
- `0x180010f18`
- `0x1800110a8`
- `0x180011384`
- `0x180011eb0`
- `0x18001217c`
- `0x18001249c`
- `0x180013280`
- `0x180013b2c`
- `0x180014128`
- `0x180014cc0`
- `0x180014ebc`
- `0x1800154e0`
- `0x1800156a0`
- `0x1800164c0`
- `0x180016778`
- `0x1800172b8`
- `0x180017398`
- `0x180017754`
- `0x18001792c`
- `0x180017aac`

## callees

- `0x180001a10`
- `0x1800181e0`

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
0x1800181e0  cmp     rcx, cs:__security_cookie
0x1800181e7  jnz     short ReportFailure
0x1800181e9  rol     rcx, 10h
0x1800181ed  test    cx, 0FFFFh
0x1800181f2  jnz     short RestoreRcx
0x1800181f4  retn
0x1800181f5  ror     rcx, 10h
0x1800181f9  jmp     __report_gsfailure
```
