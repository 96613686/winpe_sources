# __security_check_cookie

- ea: `0x1400065f0`
- end: `0x14000660e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `15`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001da8`
- `0x140001eec`
- `0x1400025a4`
- `0x1400031f4`
- `0x140003abc`
- `0x140003e48`
- `0x140003f98`
- `0x140004128`
- `0x1400042ec`
- `0x140004e78`
- `0x140004f48`
- `0x140005384`
- `0x14000552c`
- `0x1400059e8`
- `0x140005ce4`

## callees

- `0x1400016e0`
- `0x1400065f0`

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
0x1400065f0  cmp     rcx, cs:__security_cookie
0x1400065f7  jnz     short loc_140006609
0x1400065f9  rol     rcx, 10h
0x1400065fd  test    cx, 0FFFFh
0x140006602  jnz     short loc_140006605
0x140006604  retn
0x140006605  ror     rcx, 10h
0x140006609  jmp     __report_gsfailure
```
