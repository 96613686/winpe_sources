# __security_check_cookie

- ea: `0x140005e10`
- end: `0x140005e2e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `17`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001010`
- `0x1400021b0`
- `0x1400034d0`
- `0x140004a74`
- `0x140004cc0`
- `0x140005d0c`
- `0x14000e0ec`
- `0x14000ef40`
- `0x1400100ac`
- `0x140010254`
- `0x140012290`
- `0x140012de0`
- `0x140013008`
- `0x1400133f0`
- `0x1400144c4`
- `0x140017388`
- `0x140017550`

## callees

- `0x140002a80`
- `0x140005e10`

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
0x140005e10  cmp     rcx, cs:__security_cookie
0x140005e17  jnz     short ReportFailure
0x140005e19  rol     rcx, 10h
0x140005e1d  test    cx, 0FFFFh
0x140005e22  jnz     short RestoreRcx
0x140005e24  retn
0x140005e25  ror     rcx, 10h; StackCookie
0x140005e29  jmp     __report_gsfailure
```
