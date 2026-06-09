# __security_check_cookie

- ea: `0x140001fa0`
- end: `0x140001fbe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `39`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x1400012bc`
- `0x140001560`
- `0x1400032c4`
- `0x140003560`
- `0x140003688`
- `0x140003ae4`
- `0x140003ecc`
- `0x140004734`
- `0x140005024`
- `0x1400057b8`
- `0x1400058e4`
- `0x140006390`
- `0x140006570`
- `0x1400068a4`
- `0x1400086e4`
- `0x1400089a0`
- `0x140008b80`
- `0x140009124`
- `0x140009e64`
- `0x14000aac0`
- `0x14000ad38`
- `0x14000af38`
- `0x14000b960`
- `0x14000bbb0`
- `0x14000bd48`
- `0x14000be50`
- `0x14000c15c`
- `0x14000c654`
- `0x14000d138`
- `0x14000d428`
- `0x14000d578`
- `0x14000d708`
- `0x14000d8cc`
- `0x14000e07c`
- `0x14000e20c`
- `0x14000e534`
- `0x14000e89c`
- `0x14000f660`

## callees

- `0x140001fa0`
- `0x1400024d0`

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
0x140001fa0  cmp     rcx, cs:__security_cookie
0x140001fa7  jnz     short loc_140001FB9
0x140001fa9  rol     rcx, 10h
0x140001fad  test    cx, 0FFFFh
0x140001fb2  jnz     short loc_140001FB5
0x140001fb4  retn
0x140001fb5  ror     rcx, 10h; StackCookie
0x140001fb9  jmp     __report_gsfailure
```
