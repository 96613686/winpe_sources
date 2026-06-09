# __security_check_cookie

- ea: `0x180001ef0`
- end: `0x180001f0e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `20`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x180001560`
- `0x180003b0c`
- `0x180004a14`
- `0x180004cb0`
- `0x180004f6c`
- `0x1800054c4`
- `0x180005a88`
- `0x180005e80`
- `0x1800060b0`
- `0x1800065f4`
- `0x180006a14`
- `0x1800079a0`
- `0x180008cf0`
- `0x180008e98`
- `0x180009070`
- `0x18000952c`
- `0x180009ae0`
- `0x18000a184`

## callees

- `0x180001ef0`
- `0x1800024b0`

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
0x180001ef0  cmp     rcx, cs:__security_cookie
0x180001ef7  jnz     short ReportFailure
0x180001ef9  rol     rcx, 10h
0x180001efd  test    cx, 0FFFFh
0x180001f02  jnz     short RestoreRcx
0x180001f04  retn
0x180001f05  ror     rcx, 10h; StackCookie
0x180001f09  jmp     __report_gsfailure
```
