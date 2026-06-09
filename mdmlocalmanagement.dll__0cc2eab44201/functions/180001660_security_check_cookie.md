# __security_check_cookie

- ea: `0x180001660`
- end: `0x18000167e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `16`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180002624`
- `0x1800028d4`
- `0x180002f5c`
- `0x1800034b4`
- `0x180003850`
- `0x180004210`
- `0x1800051cc`
- `0x1800057a0`
- `0x1800058e0`
- `0x180005c00`
- `0x180005d20`
- `0x180006000`
- `0x1800063cc`
- `0x180006634`
- `0x1800069a8`

## callees

- `0x180001660`
- `0x180001a70`

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
0x180001660  cmp     rcx, cs:__security_cookie
0x180001667  jnz     short ReportFailure
0x180001669  rol     rcx, 10h
0x18000166d  test    cx, 0FFFFh
0x180001672  jnz     short RestoreRcx
0x180001674  retn
0x180001675  ror     rcx, 10h; StackCookie
0x180001679  jmp     __report_gsfailure
```
