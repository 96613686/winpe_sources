# __security_check_cookie

- ea: `0x180009270`
- end: `0x18000928e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `50`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001210`
- `0x1800012a0`
- `0x180001570`
- `0x180001ad0`
- `0x180002540`
- `0x180002e70`
- `0x1800039a0`
- `0x180003b40`
- `0x180004470`
- `0x1800045b0`
- `0x180004840`
- `0x180004b70`
- `0x180005100`
- `0x180005760`
- `0x180005990`
- `0x180005f60`
- `0x180006f00`
- `0x180007790`
- `0x1800079f0`
- `0x180007cf0`
- `0x180008160`
- `0x18000ae04`
- `0x18000b0a0`
- `0x18000b7d0`
- `0x18000b8d0`
- `0x18000bba0`
- `0x18000bca0`
- `0x18000c040`
- `0x18000c350`
- `0x18000cdf0`
- `0x18000cef0`
- `0x18000cfe0`
- `0x18000d6c0`
- `0x18000e0c4`
- `0x18000e608`
- `0x18000e7d4`
- `0x18000ec20`
- `0x18000f24c`
- `0x18000f330`
- `0x18000f644`
- `0x18000f6d8`
- `0x18000f8a0`
- `0x180010548`
- `0x180010e18`
- `0x180011018`
- `0x1800116d0`
- `0x1800119c0`
- `0x180011d40`
- `0x180012020`
- `0x180012644`

## callees

- `0x180009270`
- `0x1800092a0`

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
0x180009270  cmp     rcx, cs:__security_cookie
0x180009277  jnz     short ReportFailure
0x180009279  rol     rcx, 10h
0x18000927d  test    cx, 0FFFFh
0x180009282  jnz     short RestoreRcx
0x180009284  retn
0x180009285  ror     rcx, 10h; StackCookie
0x180009289  jmp     __report_gsfailure
```
