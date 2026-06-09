# __security_check_cookie

- ea: `0x180001410`
- end: `0x18000142e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `38`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001fb8`
- `0x1800025ac`
- `0x1800027cc`
- `0x1800041d0`
- `0x180004af8`
- `0x180004cf8`
- `0x180005720`
- `0x180005a54`
- `0x180005d2c`
- `0x180008960`
- `0x180009f14`
- `0x18000a748`
- `0x18000ae70`
- `0x18000b720`
- `0x18000c124`
- `0x18000c474`
- `0x18000ce28`
- `0x18000d090`
- `0x18000d6f0`
- `0x180012bfc`
- `0x18001302c`
- `0x180013548`
- `0x180013b24`
- `0x180014888`
- `0x180014e84`
- `0x180016934`
- `0x1800187e4`
- `0x180018974`
- `0x18001b834`
- `0x18001bd58`
- `0x18001be94`
- `0x18001c138`
- `0x18001c924`
- `0x18001cb2c`
- `0x18001cd90`
- `0x18001cee0`
- `0x18001d024`
- `0x18001d2ac`

## callees

- `0x180001410`
- `0x180001440`

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
0x180001410  cmp     rcx, cs:__security_cookie
0x180001417  jnz     short ReportFailure
0x180001419  rol     rcx, 10h
0x18000141d  test    cx, 0FFFFh
0x180001422  jnz     short RestoreRcx
0x180001424  retn
0x180001425  ror     rcx, 10h; StackCookie
0x180001429  jmp     __report_gsfailure
```
