# __security_check_cookie

- ea: `0x180001e70`
- end: `0x180001e8e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `27`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800012dc`
- `0x1800015d4`
- `0x180004940`
- `0x180006648`
- `0x1800068e4`
- `0x180006ea8`
- `0x180007074`
- `0x180007404`
- `0x1800077b8`
- `0x180008ea8`
- `0x1800093f0`
- `0x18000b9c0`
- `0x18000bb70`
- `0x18000c4dc`
- `0x18000c99c`
- `0x18000dd10`
- `0x18000eae0`
- `0x18000ef18`
- `0x18000f308`
- `0x18000f49c`
- `0x18000fa8c`
- `0x180011ad0`
- `0x18001240c`
- `0x180012e84`
- `0x180012f78`
- `0x180013898`

## callees

- `0x180001e70`
- `0x180002450`

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
0x180001e70  cmp     rcx, cs:__security_cookie
0x180001e77  jnz     short ReportFailure
0x180001e79  rol     rcx, 10h
0x180001e7d  test    cx, 0FFFFh
0x180001e82  jnz     short RestoreRcx
0x180001e84  retn
0x180001e85  ror     rcx, 10h; StackCookie
0x180001e89  jmp     __report_gsfailure
```
