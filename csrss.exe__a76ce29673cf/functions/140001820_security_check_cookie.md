# __security_check_cookie

- ea: `0x140001820`
- end: `0x14000183e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140001430`
- `0x140001820`

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
0x140001820  cmp     rcx, cs:__security_cookie
0x140001827  jnz     short loc_140001839
0x140001829  rol     rcx, 10h
0x14000182d  test    cx, 0FFFFh
0x140001832  jnz     short loc_140001835
0x140001834  retn
0x140001835  ror     rcx, 10h
0x140001839  jmp     __report_gsfailure
```
