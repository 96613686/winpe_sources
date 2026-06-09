# __security_check_cookie

- ea: `0x140018350`
- end: `0x14001836e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `57`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001b5c`
- `0x140002300`
- `0x140002650`
- `0x140002908`
- `0x1400030c0`
- `0x140003a48`
- `0x140004374`
- `0x140004868`
- `0x1400051c0`
- `0x140005f30`
- `0x14000664c`
- `0x1400076f4`
- `0x140007860`
- `0x140007dd0`
- `0x140008280`
- `0x1400085f0`
- `0x140008720`
- `0x140008b50`
- `0x140009180`
- `0x140009710`
- `0x140009b80`
- `0x140009cfc`
- `0x14000add4`
- `0x14000b030`
- `0x14000c80c`
- `0x14000cf28`
- `0x14000df10`
- `0x14000e120`
- `0x14000e320`
- `0x14000f4d0`
- `0x14000f66c`
- `0x14000fd50`
- `0x1400100f0`
- `0x1400104fc`
- `0x140010a1c`
- `0x1400110fc`
- `0x140011440`
- `0x1400114ac`
- `0x140011614`
- `0x140011800`
- `0x140011968`
- `0x140011b54`
- `0x140011cec`
- `0x140011e80`
- `0x1400128c8`
- `0x140012b64`
- `0x14001339c`
- `0x140013740`
- `0x140013b10`
- `0x140014574`

## callees

- `0x140001530`
- `0x140018350`

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
0x140018350  cmp     rcx, cs:__security_cookie
0x140018357  jnz     short loc_140018369
0x140018359  rol     rcx, 10h
0x14001835d  test    cx, 0FFFFh
0x140018362  jnz     short loc_140018365
0x140018364  retn
0x140018365  ror     rcx, 10h
0x140018369  jmp     __report_gsfailure
```
