# __security_check_cookie

- ea: `0x140013110`
- end: `0x14001312e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `30`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400010e0`
- `0x140002e80`
- `0x1400057d0`
- `0x140005c10`
- `0x140007260`
- `0x140009860`
- `0x14000a380`
- `0x14000adf8`
- `0x14000b2e8`
- `0x14000b4d0`
- `0x14000bd90`
- `0x14000c380`
- `0x14000d284`
- `0x14000ee88`
- `0x14000f54c`
- `0x14000f5d8`
- `0x140010040`
- `0x140011500`
- `0x14001155c`
- `0x140011670`
- `0x1400116ec`
- `0x140012410`
- `0x140012b5c`
- `0x140012ec4`
- `0x140012fdc`
- `0x14001e2dc`
- `0x14001e4dc`
- `0x14001ee0c`
- `0x14002056c`
- `0x1400209b4`

## callees

- `0x14000c7f0`
- `0x140013110`

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
0x140013110  cmp     rcx, cs:__security_cookie
0x140013117  jnz     short ReportFailure
0x140013119  rol     rcx, 10h
0x14001311d  test    cx, 0FFFFh
0x140013122  jnz     short RestoreRcx
0x140013124  retn
0x140013125  ror     rcx, 10h; StackCookie
0x140013129  jmp     __report_gsfailure
```
