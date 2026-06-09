# __security_check_cookie

- ea: `0x1400161f0`
- end: `0x14001620e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `50`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001be0`
- `0x140003970`
- `0x140003c30`
- `0x1400040a0`
- `0x1400060f0`
- `0x140008c80`
- `0x140009714`
- `0x1400097f8`
- `0x14000a190`
- `0x14000abf0`
- `0x14000b5d0`
- `0x14000d434`
- `0x14000d4e8`
- `0x14000d99c`
- `0x14000e208`
- `0x14000e400`
- `0x14000ec48`
- `0x14000f2d0`
- `0x140011780`
- `0x140011940`
- `0x1400127f0`
- `0x140012b38`
- `0x140013570`
- `0x140013c4c`
- `0x140014114`
- `0x1400147b8`
- `0x140014fb4`
- `0x140015a88`
- `0x1400160bc`
- `0x1400242d4`
- `0x140026360`
- `0x140026464`
- `0x1400288a0`
- `0x140028f60`
- `0x14002aa40`
- `0x14002b270`
- `0x14002c200`
- `0x14002e99c`
- `0x140030144`
- `0x140032cd0`
- `0x140033c30`
- `0x140035ad8`
- `0x140035f70`
- `0x1400370e8`
- `0x1400378b0`
- `0x140037c40`
- `0x140039008`
- `0x140039818`
- `0x140039a50`
- `0x140039b38`

## callees

- `0x14000a270`
- `0x1400161f0`

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
0x1400161f0  cmp     rcx, cs:__security_cookie
0x1400161f7  jnz     short ReportFailure
0x1400161f9  rol     rcx, 10h
0x1400161fd  test    cx, 0FFFFh
0x140016202  jnz     short RestoreRcx
0x140016204  retn
0x140016205  ror     rcx, 10h; StackCookie
0x140016209  jmp     __report_gsfailure
```
