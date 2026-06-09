# __security_check_cookie

- ea: `0x180016090`
- end: `0x1800160ae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `53`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800023b8`
- `0x180004fa0`
- `0x1800062e0`
- `0x1800064a0`
- `0x1800075d0`
- `0x1800086c4`
- `0x180008bc0`
- `0x180008e90`
- `0x1800098c4`
- `0x180009c00`
- `0x18000a050`
- `0x18000a9b0`
- `0x18000b09c`
- `0x18000e390`
- `0x18000ec48`
- `0x18000f240`
- `0x18000fe80`
- `0x1800103f0`
- `0x180010d90`
- `0x180011190`
- `0x1800115c0`
- `0x180011c10`
- `0x180012690`
- `0x180012d90`
- `0x180013b14`
- `0x18001466c`
- `0x180015554`
- `0x1800180f4`
- `0x1800185d8`
- `0x18001913c`
- `0x18001a2c8`
- `0x18001a5d0`
- `0x18001b9b0`
- `0x18001c250`
- `0x18001c9a4`
- `0x18001cc60`
- `0x18001cf50`
- `0x18001ddf0`
- `0x18001e4bc`
- `0x18001e910`
- `0x18001eca8`
- `0x18001f090`
- `0x18001f548`
- `0x18001f9ec`
- `0x18001fdfc`
- `0x180020250`
- `0x1800205c4`
- `0x180021a08`
- `0x180022150`
- `0x1800223d4`

## callees

- `0x180016090`
- `0x1800160c0`

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
0x180016090  cmp     rcx, cs:__security_cookie
0x180016097  jnz     short ReportFailure
0x180016099  rol     rcx, 10h
0x18001609d  test    cx, 0FFFFh
0x1800160a2  jnz     short RestoreRcx
0x1800160a4  retn
0x1800160a5  ror     rcx, 10h; StackCookie
0x1800160a9  jmp     __report_gsfailure
```
