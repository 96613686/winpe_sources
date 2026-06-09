# __security_check_cookie

- ea: `0x1400059b0`
- end: `0x1400059ce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `14`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x1400010d4`
- `0x140001184`
- `0x1400014e4`
- `0x14000244c`
- `0x140002908`
- `0x140002ba4`
- `0x140002f70`
- `0x140003138`
- `0x140003654`
- `0x140003a08`
- `0x140003fec`
- `0x140004f44`
- `0x140005910`

## callees

- `0x140002010`
- `0x1400059b0`

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
0x1400059b0  cmp     rcx, cs:__security_cookie
0x1400059b7  jnz     short loc_1400059C9
0x1400059b9  rol     rcx, 10h
0x1400059bd  test    cx, 0FFFFh
0x1400059c2  jnz     short loc_1400059C5
0x1400059c4  retn
0x1400059c5  ror     rcx, 10h
0x1400059c9  jmp     __report_gsfailure
```
