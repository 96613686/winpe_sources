# __security_check_cookie

- ea: `0x1800358a0`
- end: `0x1800358be`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `83`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001150`
- `0x180001404`
- `0x180001494`
- `0x180001738`
- `0x180001b14`
- `0x180001ba8`
- `0x180001c10`
- `0x180001cf0`
- `0x180001d9c`
- `0x180003be8`
- `0x180004240`
- `0x180004500`
- `0x180004bb0`
- `0x180004fbc`
- `0x180005534`
- `0x18000597c`
- `0x18000734c`
- `0x1800079f0`
- `0x180007d5c`
- `0x180008d50`
- `0x180009c80`
- `0x18000b330`
- `0x18000bb80`
- `0x18000bd70`
- `0x18000c7d0`
- `0x18000c8f4`
- `0x18000ca5c`
- `0x18000cbc4`
- `0x18000de00`
- `0x18000f1a0`
- `0x18000f58c`
- `0x1800118a0`
- `0x180011e80`
- `0x1800133d8`
- `0x180014454`
- `0x180014f14`
- `0x180016a90`
- `0x1800172c4`
- `0x180020c50`
- `0x180020ecc`
- `0x180021794`
- `0x180022b04`
- `0x180023680`
- `0x180024870`
- `0x180024ba0`
- `0x180025224`
- `0x180026840`
- `0x180026be4`
- `0x180026dbc`

## callees

- `0x180002aa0`
- `0x1800358a0`

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
0x1800358a0  cmp     rcx, cs:__security_cookie
0x1800358a7  jnz     short ReportFailure
0x1800358a9  rol     rcx, 10h
0x1800358ad  test    cx, 0FFFFh
0x1800358b2  jnz     short RestoreRcx
0x1800358b4  retn
0x1800358b5  ror     rcx, 10h
0x1800358b9  jmp     __report_gsfailure
```
