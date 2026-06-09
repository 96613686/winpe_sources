# __security_check_cookie

- ea: `0x180019ad0`
- end: `0x180019aee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `102`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x18000142c`
- `0x1800015a0`
- `0x18000163c`
- `0x1800016e0`
- `0x18000175c`
- `0x18000180c`
- `0x180001894`
- `0x180001930`
- `0x1800019b4`
- `0x180001ac0`
- `0x180001bb8`
- `0x180001c24`
- `0x180001ca4`
- `0x180001d04`
- `0x180001d8c`
- `0x180001e00`
- `0x180001ed4`
- `0x180002328`
- `0x1800027e0`
- `0x180003100`
- `0x180003304`
- `0x180003cc0`
- `0x18000490c`
- `0x180004b30`
- `0x180004d78`
- `0x180005014`
- `0x180005368`
- `0x1800058ec`
- `0x180006468`
- `0x180006904`
- `0x180006ed8`
- `0x180007a80`
- `0x180008440`
- `0x180009a70`
- `0x18000a260`
- `0x18000a5c0`
- `0x18000aaa0`
- `0x18000bf10`
- `0x18000ce60`
- `0x18000d6ac`
- `0x18000d90c`
- `0x18000e644`
- `0x18000e950`
- `0x18000ebc8`
- `0x18000f2a8`
- `0x18000f4fc`
- `0x18000fae0`
- `0x18000fbe4`
- `0x180010088`

## callees

- `0x180019ad0`
- `0x180019b00`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
ReportFailure:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto ReportFailure;
  }
}

```

## disassembly

```asm
0x180019ad0  cmp     rcx, cs:__security_cookie
0x180019ad7  jnz     short ReportFailure
0x180019ad9  rol     rcx, 10h
0x180019add  test    cx, 0FFFFh
0x180019ae2  jnz     short RestoreRcx
0x180019ae4  retn
0x180019ae5  ror     rcx, 10h; StackCookie
0x180019ae9  jmp     __report_gsfailure
```
