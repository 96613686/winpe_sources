# __security_check_cookie

- ea: `0x18000c3c0`
- end: `0x18000c3de`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `17`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x1800029f4`
- `0x18000356c`
- `0x180003604`
- `0x180004630`
- `0x1800076b4`
- `0x1800083cc`
- `0x180008a54`
- `0x180008cf0`
- `0x180008fc8`
- `0x18000936c`
- `0x1800098cc`
- `0x18000a5f4`
- `0x18000aeb4`
- `0x18000c244`
- `0x18000c314`

## callees

- `0x180002090`
- `0x18000c3c0`

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
0x18000c3c0  cmp     rcx, cs:__security_cookie
0x18000c3c7  jnz     short ReportFailure
0x18000c3c9  rol     rcx, 10h
0x18000c3cd  test    cx, 0FFFFh
0x18000c3d2  jnz     short RestoreRcx
0x18000c3d4  retn
0x18000c3d5  ror     rcx, 10h
0x18000c3d9  jmp     __report_gsfailure
```
