# __security_check_cookie

- ea: `0x1400054a0`
- end: `0x1400054be`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `22`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002668`
- `0x140003990`
- `0x1400041b8`
- `0x14000426c`
- `0x140004304`
- `0x1400043ec`
- `0x1400044bc`
- `0x14000458c`
- `0x140005044`
- `0x14000536c`
- `0x14000f008`
- `0x140010c94`
- `0x140010d68`
- `0x1400118fc`
- `0x140012040`
- `0x14001379c`
- `0x140016320`
- `0x140016a34`
- `0x140016dc4`
- `0x140017cb0`
- `0x140018c10`
- `0x1400211b4`

## callees

- `0x140002850`
- `0x1400054a0`

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
0x1400054a0  cmp     rcx, cs:__security_cookie
0x1400054a7  jnz     short ReportFailure
0x1400054a9  rol     rcx, 10h
0x1400054ad  test    cx, 0FFFFh
0x1400054b2  jnz     short RestoreRcx
0x1400054b4  retn
0x1400054b5  ror     rcx, 10h; StackCookie
0x1400054b9  jmp     __report_gsfailure
```
