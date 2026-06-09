# __security_check_cookie

- ea: `0x1800054b0`
- end: `0x1800054ce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `15`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001c20`
- `0x180001da0`
- `0x180002144`
- `0x1800029d4`
- `0x180002af0`
- `0x180003240`
- `0x180003420`
- `0x1800044c8`
- `0x180004564`
- `0x180004630`
- `0x1800047e0`
- `0x180004c60`
- `0x180004d54`
- `0x180004e1c`
- `0x1800053b0`

## callees

- `0x180001530`
- `0x1800054b0`

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
0x1800054b0  cmp     rcx, cs:__security_cookie
0x1800054b7  jnz     short ReportFailure
0x1800054b9  rol     rcx, 10h
0x1800054bd  test    cx, 0FFFFh
0x1800054c2  jnz     short RestoreRcx
0x1800054c4  retn
0x1800054c5  ror     rcx, 10h
0x1800054c9  jmp     __report_gsfailure
```
