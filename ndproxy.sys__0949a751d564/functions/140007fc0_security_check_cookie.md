# __security_check_cookie

- ea: `0x140007fc0`
- end: `0x140007fde`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `22`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001680`
- `0x140002670`
- `0x140002fd0`
- `0x1400058d4`
- `0x140005ca4`
- `0x1400062c0`
- `0x140007e8c`
- `0x14000f020`
- `0x14000f250`
- `0x14000f830`
- `0x14000fcb0`
- `0x140010600`
- `0x140010924`
- `0x140012210`
- `0x140012590`
- `0x1400130a0`
- `0x140013bc0`
- `0x140014310`
- `0x140015290`
- `0x14001591c`
- `0x1400183b8`
- `0x140018f2c`

## callees

- `0x140001010`
- `0x140007fc0`

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
0x140007fc0  cmp     rcx, cs:__security_cookie
0x140007fc7  jnz     short ReportFailure
0x140007fc9  rol     rcx, 10h
0x140007fcd  test    cx, 0FFFFh
0x140007fd2  jnz     short RestoreRcx
0x140007fd4  retn
0x140007fd5  ror     rcx, 10h; StackCookie
0x140007fd9  jmp     __report_gsfailure
```
