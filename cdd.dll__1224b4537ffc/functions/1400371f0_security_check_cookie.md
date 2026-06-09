# __security_check_cookie

- ea: `0x1400371f0`
- end: `0x14003720e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `77`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400015e0`
- `0x140001cb4`
- `0x140001dcc`
- `0x140001f04`
- `0x140002130`
- `0x140002504`
- `0x140004904`
- `0x140005cc0`
- `0x140006a70`
- `0x140007b00`
- `0x14000919c`
- `0x14000a254`
- `0x14000c1cc`
- `0x14000cb44`
- `0x14000d63c`
- `0x14000dfd0`
- `0x14000e420`
- `0x14000e790`
- `0x140010c2c`
- `0x140011510`
- `0x140012f10`
- `0x1400133d0`
- `0x140013db0`
- `0x140014338`
- `0x140014670`
- `0x140014ab0`
- `0x1400161b0`
- `0x140017518`
- `0x140019458`
- `0x14001b448`
- `0x14001c9e4`
- `0x14001d1b0`
- `0x14001d980`
- `0x14001ef90`
- `0x1400200e8`
- `0x140020960`
- `0x1400212b0`
- `0x140022270`
- `0x1400224a0`
- `0x140022e70`
- `0x1400235c0`
- `0x140023e60`
- `0x1400248f8`
- `0x140024cb4`
- `0x140025090`
- `0x1400255b0`
- `0x140025c90`
- `0x1400261a0`
- `0x1400267f0`
- `0x140026d40`

## callees

- `0x140029420`
- `0x1400371f0`

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
0x1400371f0  cmp     rcx, cs:__security_cookie
0x1400371f7  jnz     short ReportFailure
0x1400371f9  rol     rcx, 10h
0x1400371fd  test    cx, 0FFFFh
0x140037202  jnz     short RestoreRcx
0x140037204  retn
0x140037205  ror     rcx, 10h; StackCookie
0x140037209  jmp     __report_gsfailure
```
