# __security_check_cookie

- ea: `0x18000c600`
- end: `0x18000c61e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `34`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000112c`
- `0x180001248`
- `0x180001340`
- `0x1800013d0`
- `0x180002818`
- `0x180002ac4`
- `0x180003140`
- `0x180003524`
- `0x180003a74`
- `0x180003df0`
- `0x18000564c`
- `0x180005e40`
- `0x180006030`
- `0x18000630c`
- `0x180006b10`
- `0x1800071d8`
- `0x180007360`
- `0x180008670`
- `0x1800089c0`
- `0x180008cc0`
- `0x180008fc0`
- `0x180009290`
- `0x18000a0dc`
- `0x18000a7f8`
- `0x18000aa94`
- `0x18000acc4`
- `0x18000af48`
- `0x18000b1c8`
- `0x18000b3f0`
- `0x18000b660`
- `0x18000b7dc`
- `0x18000be80`
- `0x18000c144`
- `0x18000c4e0`

## callees

- `0x180002000`
- `0x18000c600`

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
0x18000c600  cmp     rcx, cs:__security_cookie
0x18000c607  jnz     short ReportFailure
0x18000c609  rol     rcx, 10h
0x18000c60d  test    cx, 0FFFFh
0x18000c612  jnz     short RestoreRcx
0x18000c614  retn
0x18000c615  ror     rcx, 10h
0x18000c619  jmp     __report_gsfailure
```
