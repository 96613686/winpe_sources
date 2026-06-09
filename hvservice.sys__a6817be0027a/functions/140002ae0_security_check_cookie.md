# __security_check_cookie

- ea: `0x140002ae0`
- end: `0x140002afe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `31`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001600`
- `0x14000220c`
- `0x140002254`
- `0x1400022b4`
- `0x14000234c`
- `0x14000292c`
- `0x14000e61c`
- `0x14000e7b8`
- `0x14000e9a4`
- `0x14000eab0`
- `0x14000ecd0`
- `0x14000fee8`
- `0x1400101d0`
- `0x140010320`
- `0x140010914`
- `0x140010a78`
- `0x1400115a0`
- `0x140012170`
- `0x140012524`
- `0x140012658`
- `0x14001274c`
- `0x140012c40`
- `0x140012e9c`
- `0x140013510`
- `0x14001396c`
- `0x140013a60`
- `0x140013b34`
- `0x140013c34`
- `0x140013dc4`
- `0x140014810`
- `0x140015078`

## callees

- `0x1400015d0`
- `0x140002ae0`

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
0x140002ae0  cmp     rcx, cs:__security_cookie
0x140002ae7  jnz     short ReportFailure
0x140002ae9  rol     rcx, 10h
0x140002aed  test    cx, 0FFFFh
0x140002af2  jnz     short RestoreRcx
0x140002af4  retn
0x140002af5  ror     rcx, 10h; StackCookie
0x140002af9  jmp     __report_gsfailure
```
