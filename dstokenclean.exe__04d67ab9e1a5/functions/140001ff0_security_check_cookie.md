# __security_check_cookie

- ea: `0x140001ff0`
- end: `0x14000200e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001b0c`
- `0x140001bcc`
- `0x140001e5c`
- `0x140001f60`

## callees

- `0x140001740`
- `0x140001ff0`

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
0x140001ff0  cmp     rcx, cs:__security_cookie
0x140001ff7  jnz     short loc_140002009
0x140001ff9  rol     rcx, 10h
0x140001ffd  test    cx, 0FFFFh
0x140002002  jnz     short loc_140002005
0x140002004  retn
0x140002005  ror     rcx, 10h
0x140002009  jmp     __report_gsfailure
```
