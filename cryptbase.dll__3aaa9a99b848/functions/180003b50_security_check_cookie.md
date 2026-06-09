# __security_check_cookie

- ea: `0x180003b50`
- end: `0x180003b6e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001820`
- `0x180001a50`
- `0x180001c00`
- `0x180001f50`
- `0x180002350`
- `0x180002500`
- `0x180002b3c`
- `0x180002bdc`
- `0x180002c90`
- `0x180003aa8`

## callees

- `0x1800026b0`
- `0x180003b50`

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
0x180003b50  cmp     rcx, cs:__security_cookie
0x180003b57  jnz     short loc_180003B69
0x180003b59  rol     rcx, 10h
0x180003b5d  test    cx, 0FFFFh
0x180003b62  jnz     short loc_180003B65
0x180003b64  retn
0x180003b65  ror     rcx, 10h
0x180003b69  jmp     __report_gsfailure
```
