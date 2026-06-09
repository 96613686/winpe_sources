# __security_check_cookie

- ea: `0x180001500`
- end: `0x18000151e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `14`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002308`
- `0x1800033d8`
- `0x1800038f4`
- `0x1800047a0`
- `0x1800051b4`
- `0x18000589c`
- `0x180005b30`
- `0x1800060c8`
- `0x180006498`
- `0x180006a04`
- `0x180006d80`
- `0x18000857c`
- `0x180008a40`
- `0x180008c60`

## callees

- `0x180001500`
- `0x180001b60`

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
0x180001500  cmp     rcx, cs:__security_cookie
0x180001507  jnz     short ReportFailure
0x180001509  rol     rcx, 10h
0x18000150d  test    cx, 0FFFFh
0x180001512  jnz     short RestoreRcx
0x180001514  retn
0x180001515  ror     rcx, 10h; StackCookie
0x180001519  jmp     __report_gsfailure
```
