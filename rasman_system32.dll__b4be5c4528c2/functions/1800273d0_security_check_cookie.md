# __security_check_cookie

- ea: `0x1800273d0`
- end: `0x1800273ee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `21`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001160`
- `0x1800016f0`
- `0x180001ff0`
- `0x180002d60`
- `0x1800030d0`
- `0x180011d34`
- `0x180014570`
- `0x1800182f0`
- `0x18001e9c0`
- `0x18001eb40`
- `0x18001ed70`
- `0x180020d30`
- `0x18002293c`
- `0x180024290`
- `0x1800244b8`
- `0x18002464c`
- `0x1800246c4`
- `0x1800247b4`
- `0x180024954`
- `0x180025dec`
- `0x1800272ac`

## callees

- `0x180015d20`
- `0x1800273d0`

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
0x1800273d0  cmp     rcx, cs:__security_cookie
0x1800273d7  jnz     short ReportFailure
0x1800273d9  rol     rcx, 10h
0x1800273dd  test    cx, 0FFFFh
0x1800273e2  jnz     short RestoreRcx
0x1800273e4  retn
0x1800273e5  ror     rcx, 10h
0x1800273e9  jmp     __report_gsfailure
```
