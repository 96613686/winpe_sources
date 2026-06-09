# __security_check_cookie

- ea: `0x180006e90`
- end: `0x180006eae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000337c`
- `0x1800047f0`
- `0x180004e50`
- `0x1800057b0`
- `0x180005a54`
- `0x180005cfc`
- `0x180006114`
- `0x180006dd0`

## callees

- `0x180001790`
- `0x180006e90`

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
0x180006e90  cmp     rcx, cs:__security_cookie
0x180006e97  jnz     short ReportFailure
0x180006e99  rol     rcx, 10h
0x180006e9d  test    cx, 0FFFFh
0x180006ea2  jnz     short RestoreRcx
0x180006ea4  retn
0x180006ea5  ror     rcx, 10h
0x180006ea9  jmp     __report_gsfailure
```
