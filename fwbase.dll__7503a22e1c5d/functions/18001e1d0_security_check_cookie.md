# __security_check_cookie

- ea: `0x18001e1d0`
- end: `0x18001e1ee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `101`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001344`
- `0x180001720`
- `0x180001820`
- `0x180001b80`
- `0x180001da0`
- `0x180002280`
- `0x180002610`
- `0x180002910`
- `0x180002c10`
- `0x180002e70`
- `0x1800030b0`
- `0x1800031a0`
- `0x1800032e0`
- `0x180003b30`
- `0x180004100`
- `0x1800043a0`
- `0x1800048c0`
- `0x180004cd0`
- `0x1800050c0`
- `0x180005ca4`
- `0x180006090`
- `0x1800066f8`
- `0x1800068e4`
- `0x180006d60`
- `0x180007040`
- `0x18000c25c`
- `0x18000ccd4`
- `0x18000cdf0`
- `0x18000d2cc`
- `0x18000d364`
- `0x1800114a0`
- `0x180011f2c`
- `0x180012288`
- `0x180012a60`
- `0x180012de4`
- `0x180012f90`
- `0x180013140`
- `0x180013590`
- `0x180014130`
- `0x1800169f0`
- `0x180017044`
- `0x18001f260`
- `0x18001f3a0`
- `0x18001f794`
- `0x18001f88c`
- `0x18001f990`
- `0x18001fb90`
- `0x18001fd70`
- `0x18001ff04`
- `0x18001ff80`

## callees

- `0x18001e1d0`
- `0x18001e790`

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
0x18001e1d0  cmp     rcx, cs:__security_cookie
0x18001e1d7  jnz     short ReportFailure
0x18001e1d9  rol     rcx, 10h
0x18001e1dd  test    cx, 0FFFFh
0x18001e1e2  jnz     short RestoreRcx
0x18001e1e4  retn
0x18001e1e5  ror     rcx, 10h; StackCookie
0x18001e1e9  jmp     __report_gsfailure
```
