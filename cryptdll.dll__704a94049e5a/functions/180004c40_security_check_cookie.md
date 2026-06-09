# __security_check_cookie

- ea: `0x180004c40`
- end: `0x180004c5e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `24`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001520`
- `0x180001660`
- `0x1800017c0`
- `0x180001b90`
- `0x180001e20`
- `0x1800022c0`
- `0x1800027a0`
- `0x180002af0`
- `0x180002d80`
- `0x180003110`
- `0x180003320`
- `0x180005934`
- `0x180005c20`
- `0x180005eac`
- `0x1800060a0`
- `0x180006250`
- `0x180006350`
- `0x180006b18`
- `0x180006cd0`
- `0x1800070e0`
- `0x18000750c`
- `0x180007710`
- `0x180007870`
- `0x1800083ac`

## callees

- `0x180004c40`
- `0x180005170`

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
0x180004c40  cmp     rcx, cs:__security_cookie
0x180004c47  jnz     short ReportFailure
0x180004c49  rol     rcx, 10h
0x180004c4d  test    cx, 0FFFFh
0x180004c52  jnz     short RestoreRcx
0x180004c54  retn
0x180004c55  ror     rcx, 10h; StackCookie
0x180004c59  jmp     __report_gsfailure
```
