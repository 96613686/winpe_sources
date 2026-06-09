# __security_check_cookie

- ea: `0x180005ff0`
- end: `0x18000600e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `15`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000160c`
- `0x180001810`
- `0x180001a44`
- `0x180001bfc`
- `0x180001eec`
- `0x1800022c0`
- `0x1800025fc`
- `0x180002a90`
- `0x180002d90`
- `0x180002eac`
- `0x180003520`
- `0x1800036e0`
- `0x1800038ac`
- `0x180005ea4`
- `0x180005f6c`

## callees

- `0x180001110`
- `0x180005ff0`

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
0x180005ff0  cmp     rcx, cs:__security_cookie
0x180005ff7  jnz     short loc_180006009
0x180005ff9  rol     rcx, 10h
0x180005ffd  test    cx, 0FFFFh
0x180006002  jnz     short loc_180006005
0x180006004  retn
0x180006005  ror     rcx, 10h
0x180006009  jmp     __report_gsfailure
```
