# __security_check_cookie

- ea: `0x1400020b0`
- end: `0x1400020ce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `57`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x1400012bc`
- `0x14000134c`
- `0x1400015f0`
- `0x1400018e8`
- `0x1400033dc`
- `0x14000369c`
- `0x140003840`
- `0x140003ca0`
- `0x14000418c`
- `0x140004568`
- `0x140004b34`
- `0x14000550c`
- `0x140005fbc`
- `0x1400060a8`
- `0x140006188`
- `0x1400066e0`
- `0x1400078e4`
- `0x140008a6c`
- `0x140009260`
- `0x14000a340`
- `0x14000a7a4`
- `0x14000b2ec`
- `0x14000c064`
- `0x14000e284`
- `0x14000e5a8`
- `0x14000f0d4`
- `0x14000fa88`
- `0x14000fccc`
- `0x140011750`
- `0x1400118a4`
- `0x1400119cc`
- `0x1400121d0`
- `0x140012390`
- `0x140012430`
- `0x1400124d0`
- `0x140012570`
- `0x140012610`
- `0x1400126b0`
- `0x140012750`
- `0x1400127f0`
- `0x140016494`
- `0x140018588`
- `0x1400187e4`
- `0x14001bf5c`
- `0x14001c6e4`
- `0x14001cf68`
- `0x14001dadc`
- `0x140020538`
- `0x14002307c`

## callees

- `0x1400020b0`
- `0x140002660`

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
0x1400020b0  cmp     rcx, cs:__security_cookie
0x1400020b7  jnz     short loc_1400020C9
0x1400020b9  rol     rcx, 10h
0x1400020bd  test    cx, 0FFFFh
0x1400020c2  jnz     short loc_1400020C5
0x1400020c4  retn
0x1400020c5  ror     rcx, 10h; StackCookie
0x1400020c9  jmp     __report_gsfailure
```
