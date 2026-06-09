# __security_check_cookie

- ea: `0x140001380`
- end: `0x14000139e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001ed8`
- `0x140002174`
- `0x140002374`
- `0x140002630`
- `0x140002fa8`
- `0x1400031d0`

## callees

- `0x140001380`
- `0x140001940`

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
0x140001380  cmp     rcx, cs:__security_cookie
0x140001387  jnz     short loc_140001399
0x140001389  rol     rcx, 10h
0x14000138d  test    cx, 0FFFFh
0x140001392  jnz     short loc_140001395
0x140001394  retn
0x140001395  ror     rcx, 10h; StackCookie
0x140001399  jmp     __report_gsfailure
```
