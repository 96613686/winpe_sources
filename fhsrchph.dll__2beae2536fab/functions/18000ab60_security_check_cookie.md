# __security_check_cookie

- ea: `0x18000ab60`
- end: `0x18000ab7e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `21`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001f44`
- `0x18000206c`
- `0x1800022c4`
- `0x1800037ac`
- `0x180004020`
- `0x180004a00`
- `0x180004d4c`
- `0x1800051a8`
- `0x1800052f8`
- `0x180005488`
- `0x18000566c`
- `0x180006074`
- `0x180006164`
- `0x180006c80`
- `0x180006dc0`
- `0x180007178`
- `0x1800077b0`
- `0x1800090c8`
- `0x1800093b4`
- `0x180009604`
- `0x1800099e4`

## callees

- `0x180001960`
- `0x18000ab60`

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
0x18000ab60  cmp     rcx, cs:__security_cookie
0x18000ab67  jnz     short ReportFailure
0x18000ab69  rol     rcx, 10h
0x18000ab6d  test    cx, 0FFFFh
0x18000ab72  jnz     short RestoreRcx
0x18000ab74  retn
0x18000ab75  ror     rcx, 10h
0x18000ab79  jmp     __report_gsfailure
```
