# __security_check_cookie

- ea: `0x140030f40`
- end: `0x140030f5e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `65`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001938`
- `0x140001b9c`
- `0x140001ee4`
- `0x14000508c`
- `0x140006c80`
- `0x140007354`
- `0x140009150`
- `0x14000e31c`
- `0x14000eef8`
- `0x140010c90`
- `0x140012694`
- `0x140012a10`
- `0x140013a18`
- `0x140015818`
- `0x140019e84`
- `0x14001a0e0`
- `0x14001aa0c`
- `0x14001b564`
- `0x14001b688`
- `0x14001bea8`
- `0x14001d0b4`
- `0x14001f7d0`
- `0x140021ff8`
- `0x1400232bc`
- `0x140026380`
- `0x1400288b8`
- `0x140028c9c`
- `0x140028fb0`
- `0x14002b540`
- `0x14002bb80`
- `0x14002c018`
- `0x14002c70c`
- `0x14002d08c`
- `0x14002d2d8`
- `0x14002eca4`
- `0x14002ed38`
- `0x14002fcf4`
- `0x140030bc8`
- `0x140030dec`
- `0x1400444e4`
- `0x140044b18`
- `0x140045070`
- `0x140045254`
- `0x140045570`
- `0x1400456f4`
- `0x140045798`
- `0x140046508`
- `0x1400470b4`
- `0x1400471c0`
- `0x140047630`

## callees

- `0x140028820`
- `0x140030f40`

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
0x140030f40  cmp     rcx, cs:__security_cookie
0x140030f47  jnz     short ReportFailure
0x140030f49  rol     rcx, 10h
0x140030f4d  test    cx, 0FFFFh
0x140030f52  jnz     short RestoreRcx
0x140030f54  retn
0x140030f55  ror     rcx, 10h; StackCookie
0x140030f59  jmp     __report_gsfailure
```
