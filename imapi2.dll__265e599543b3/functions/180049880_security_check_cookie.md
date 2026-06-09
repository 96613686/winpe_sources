# __security_check_cookie

- ea: `0x180049880`
- end: `0x18004989e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `88`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001890`
- `0x180001f50`
- `0x1800028d0`
- `0x180003b00`
- `0x180004af0`
- `0x1800063f8`
- `0x1800064e4`
- `0x180008760`
- `0x180008954`
- `0x18000a8ac`
- `0x18000ac88`
- `0x18000b7c8`
- `0x18000bba0`
- `0x18000f970`
- `0x180010a6c`
- `0x180010bbc`
- `0x180011508`
- `0x180012918`
- `0x180012d14`
- `0x180012e28`
- `0x180012f9c`
- `0x180013134`
- `0x1800138ec`
- `0x180013ad8`
- `0x180013dac`
- `0x180016f80`
- `0x1800185a0`
- `0x180018e80`
- `0x180019920`
- `0x180019a00`
- `0x180019dc8`
- `0x18001b104`
- `0x18001b910`
- `0x18001c518`
- `0x18001cdf4`
- `0x18001dd30`
- `0x18002135c`
- `0x180025080`
- `0x1800251a0`
- `0x180026a40`
- `0x180026b20`
- `0x180026e70`
- `0x180027370`
- `0x1800274f8`
- `0x1800280c0`
- `0x180028310`
- `0x180028680`
- `0x180028d20`
- `0x180029fd0`
- `0x18002a6a0`

## callees

- `0x1800103d0`
- `0x180049880`

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
0x180049880  cmp     rcx, cs:__security_cookie
0x180049887  jnz     short ReportFailure
0x180049889  rol     rcx, 10h
0x18004988d  test    cx, 0FFFFh
0x180049892  jnz     short RestoreRcx
0x180049894  retn
0x180049895  ror     rcx, 10h
0x180049899  jmp     __report_gsfailure
```
