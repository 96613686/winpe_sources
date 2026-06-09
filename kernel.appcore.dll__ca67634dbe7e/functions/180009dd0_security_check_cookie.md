# __security_check_cookie

- ea: `0x180009dd0`
- end: `0x180009dee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `18`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001790`
- `0x180001920`
- `0x180002b70`
- `0x180003350`
- `0x180003640`
- `0x1800038d0`
- `0x180004700`
- `0x180005160`
- `0x180005390`
- `0x18000595c`
- `0x180006354`
- `0x18000641c`
- `0x180007ec0`
- `0x180008340`
- `0x1800083f4`
- `0x180009360`
- `0x18000956c`
- `0x180009cac`

## callees

- `0x180006620`
- `0x180009dd0`

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
0x180009dd0  cmp     rcx, cs:__security_cookie
0x180009dd7  jnz     short loc_180009DE9
0x180009dd9  rol     rcx, 10h
0x180009ddd  test    cx, 0FFFFh
0x180009de2  jnz     short loc_180009DE5
0x180009de4  retn
0x180009de5  ror     rcx, 10h
0x180009de9  jmp     __report_gsfailure
```
