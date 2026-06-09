# __security_check_cookie

- ea: `0x14002c6d0`
- end: `0x14002c6ee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `13`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400069b8`
- `0x140006b08`
- `0x140006f00`
- `0x1400078cc`
- `0x1400101b8`
- `0x140010404`
- `0x14001066c`
- `0x14001f074`
- `0x14002be04`
- `0x14002c44c`
- `0x1400438d8`
- `0x14004444c`
- `0x140045078`

## callees

- `0x140001010`
- `0x14002c6d0`

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
0x14002c6d0  cmp     rcx, cs:__security_cookie
0x14002c6d7  jnz     short ReportFailure
0x14002c6d9  rol     rcx, 10h
0x14002c6dd  test    cx, 0FFFFh
0x14002c6e2  jnz     short RestoreRcx
0x14002c6e4  retn
0x14002c6e5  ror     rcx, 10h; StackCookie
0x14002c6e9  jmp     __report_gsfailure
```
