# __security_check_cookie

- ea: `0x180005c60`
- end: `0x180005c7e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `13`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001558`
- `0x180002320`
- `0x1800029f4`
- `0x180003114`
- `0x180003208`
- `0x180003e60`
- `0x1800040dc`
- `0x180004318`
- `0x180004508`
- `0x180005430`
- `0x18000585c`
- `0x180005998`
- `0x180005bb4`

## callees

- `0x180001010`
- `0x180005c60`

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
0x180005c60  cmp     rcx, cs:__security_cookie
0x180005c67  jnz     short loc_180005C79
0x180005c69  rol     rcx, 10h
0x180005c6d  test    cx, 0FFFFh
0x180005c72  jnz     short loc_180005C75
0x180005c74  retn
0x180005c75  ror     rcx, 10h
0x180005c79  jmp     __report_gsfailure
```
