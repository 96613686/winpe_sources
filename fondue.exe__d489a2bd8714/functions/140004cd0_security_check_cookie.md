# __security_check_cookie

- ea: `0x140004cd0`
- end: `0x140004cee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `12`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001b28`
- `0x140001be4`
- `0x140001d5c`
- `0x140001e24`
- `0x1400025a4`
- `0x140002840`
- `0x140002ab8`
- `0x140002e5c`
- `0x1400033a4`
- `0x14000371c`
- `0x140004840`
- `0x140004c4c`

## callees

- `0x1400018d0`
- `0x140004cd0`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
LABEL_4:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto LABEL_4;
  }
}

```

## disassembly

```asm
0x140004cd0  cmp     rcx, cs:__security_cookie
0x140004cd7  jnz     short loc_140004CE9
0x140004cd9  rol     rcx, 10h
0x140004cdd  test    cx, 0FFFFh
0x140004ce2  jnz     short loc_140004CE5
0x140004ce4  retn
0x140004ce5  ror     rcx, 10h
0x140004ce9  jmp     __report_gsfailure
```
