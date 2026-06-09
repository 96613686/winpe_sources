# __security_check_cookie

- ea: `0x18000ad30`
- end: `0x18000ad4e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `20`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001410`
- `0x180001c10`
- `0x180002f70`
- `0x1800033fc`
- `0x180003c8c`
- `0x180005370`
- `0x180005464`
- `0x180005ca8`
- `0x180005e10`
- `0x180005fd8`
- `0x180006684`
- `0x180006a38`
- `0x1800078e0`
- `0x1800080e0`
- `0x1800083d8`
- `0x180009374`
- `0x180009c88`
- `0x180009f80`
- `0x18000a168`
- `0x18000ab6c`

## callees

- `0x1800049e0`
- `0x18000ad30`

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
0x18000ad30  cmp     rcx, cs:__security_cookie
0x18000ad37  jnz     short ReportFailure
0x18000ad39  rol     rcx, 10h
0x18000ad3d  test    cx, 0FFFFh
0x18000ad42  jnz     short RestoreRcx
0x18000ad44  retn
0x18000ad45  ror     rcx, 10h
0x18000ad49  jmp     __report_gsfailure
```
