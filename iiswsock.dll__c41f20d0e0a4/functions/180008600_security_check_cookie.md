# __security_check_cookie

- ea: `0x180008600`
- end: `0x18000861e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001928`
- `0x180001a70`
- `0x180001bb8`
- `0x180006790`
- `0x180006c98`
- `0x18000838c`
- `0x180008540`

## callees

- `0x180001780`
- `0x180008600`

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
0x180008600  cmp     rcx, cs:__security_cookie
0x180008607  jnz     short ReportFailure
0x180008609  rol     rcx, 10h
0x18000860d  test    cx, 0FFFFh
0x180008612  jnz     short RestoreRcx
0x180008614  retn
0x180008615  ror     rcx, 10h
0x180008619  jmp     __report_gsfailure
```
