# __security_check_cookie

- ea: `0x18000c970`
- end: `0x18000c98e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `31`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180001320`
- `0x180001d20`
- `0x180002c60`
- `0x180002fc0`
- `0x180003a20`
- `0x1800048a0`
- `0x180004bf0`
- `0x1800052a0`
- `0x1800057f0`
- `0x1800060a0`
- `0x1800064e0`
- `0x180006920`
- `0x180006f50`
- `0x1800071c0`
- `0x1800074f0`
- `0x1800077a0`
- `0x180007930`
- `0x180007a90`
- `0x180007bf0`
- `0x180007d40`
- `0x1800082a0`
- `0x1800084b0`
- `0x18000a794`
- `0x18000ae64`
- `0x18000b838`
- `0x18000be8c`
- `0x18000bfdc`
- `0x18000c21c`
- `0x18000c418`
- `0x18000c898`

## callees

- `0x180009040`
- `0x18000c970`

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
0x18000c970  cmp     rcx, cs:__security_cookie
0x18000c977  jnz     short ReportFailure
0x18000c979  rol     rcx, 10h
0x18000c97d  test    cx, 0FFFFh
0x18000c982  jnz     short RestoreRcx
0x18000c984  retn
0x18000c985  ror     rcx, 10h
0x18000c989  jmp     __report_gsfailure
```
