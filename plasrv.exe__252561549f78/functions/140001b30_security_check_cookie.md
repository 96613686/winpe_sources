# __security_check_cookie

- ea: `0x140001b30`
- end: `0x140001b4e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001984`
- `0x140001aa8`

## callees

- `0x140001730`
- `0x140001b30`

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
0x140001b30  cmp     rcx, cs:__security_cookie
0x140001b37  jnz     short loc_140001B49
0x140001b39  rol     rcx, 10h
0x140001b3d  test    cx, 0FFFFh
0x140001b42  jnz     short loc_140001B45
0x140001b44  retn
0x140001b45  ror     rcx, 10h
0x140001b49  jmp     __report_gsfailure
```
