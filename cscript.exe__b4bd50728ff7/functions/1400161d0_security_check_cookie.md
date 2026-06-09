# __security_check_cookie

- ea: `0x1400161d0`
- end: `0x1400161ee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `63`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001330`
- `0x1400014b0`
- `0x140001950`
- `0x140001bd0`
- `0x140001edc`
- `0x140002180`
- `0x140002260`
- `0x140002a70`
- `0x1400034b4`
- `0x14000380c`
- `0x1400038e8`
- `0x140003e2c`
- `0x1400043bc`
- `0x1400046bc`
- `0x140004b50`
- `0x140004fd0`
- `0x1400051cc`
- `0x140005418`
- `0x140005610`
- `0x140005760`
- `0x1400058b4`
- `0x140005a88`
- `0x1400069d0`
- `0x140007010`
- `0x140008530`
- `0x140008ec4`
- `0x1400090b4`
- `0x140009654`
- `0x1400098d4`
- `0x14000a99c`
- `0x14000ac38`
- `0x14000b004`
- `0x14000b1fc`
- `0x14000b49c`
- `0x14000c5f8`
- `0x14000cf38`
- `0x14000d4a8`
- `0x14000d674`
- `0x14000dab0`
- `0x14000dc24`
- `0x14000ed30`
- `0x14000ee7c`
- `0x14000f08c`
- `0x14000f378`
- `0x14000f464`
- `0x14000f7d8`
- `0x14000fb28`
- `0x140010d64`
- `0x140010fd4`
- `0x1400120b0`

## callees

- `0x140009e10`
- `0x1400161d0`

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
0x1400161d0  cmp     rcx, cs:__security_cookie
0x1400161d7  jnz     short loc_1400161E9
0x1400161d9  rol     rcx, 10h
0x1400161dd  test    cx, 0FFFFh
0x1400161e2  jnz     short loc_1400161E5
0x1400161e4  retn
0x1400161e5  ror     rcx, 10h
0x1400161e9  jmp     __report_gsfailure
```
