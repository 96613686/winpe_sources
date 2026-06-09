# __security_check_cookie

- ea: `0x1400047f0`
- end: `0x14000480e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `23`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001470`
- `0x1400024e0`
- `0x140004154`
- `0x14000447c`
- `0x1400046bc`
- `0x140010388`
- `0x1400109d0`
- `0x140011288`
- `0x140013edc`
- `0x1400152b0`
- `0x1400154b8`
- `0x1400175f0`
- `0x140017b90`
- `0x1400184d4`
- `0x1400187ac`
- `0x1400189fc`
- `0x140018d0c`
- `0x140019358`
- `0x14001b1e0`
- `0x14001c1b0`
- `0x14001d600`
- `0x14001ddf0`
- `0x140020600`

## callees

- `0x140001cc0`
- `0x1400047f0`

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
0x1400047f0  cmp     rcx, cs:__security_cookie
0x1400047f7  jnz     short ReportFailure
0x1400047f9  rol     rcx, 10h
0x1400047fd  test    cx, 0FFFFh
0x140004802  jnz     short RestoreRcx
0x140004804  retn
0x140004805  ror     rcx, 10h; StackCookie
0x140004809  jmp     __report_gsfailure
```
