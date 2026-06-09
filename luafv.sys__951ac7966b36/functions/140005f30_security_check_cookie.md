# __security_check_cookie

- ea: `0x140005f30`
- end: `0x140005f4e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `36`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002af8`
- `0x1400031d8`
- `0x140005e3c`
- `0x1400140b4`
- `0x1400143e8`
- `0x140014474`
- `0x140014970`
- `0x140015078`
- `0x140015388`
- `0x1400161c0`
- `0x140016238`
- `0x1400162cc`
- `0x140016c50`
- `0x140016d94`
- `0x140016ec8`
- `0x140017afc`
- `0x140017c54`
- `0x1400181f4`
- `0x140018530`
- `0x14001860c`
- `0x140018680`
- `0x1400187b0`
- `0x140018f70`
- `0x140019780`
- `0x14001af8c`
- `0x14001c420`
- `0x14001e770`
- `0x14001ea60`
- `0x140020450`
- `0x140021e90`
- `0x1400230a8`
- `0x140023d14`
- `0x1400247e0`
- `0x140028714`
- `0x1400291a8`
- `0x140029574`

## callees

- `0x140002270`
- `0x140005f30`

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
0x140005f30  cmp     rcx, cs:__security_cookie
0x140005f37  jnz     short ReportFailure
0x140005f39  rol     rcx, 10h
0x140005f3d  test    cx, 0FFFFh
0x140005f42  jnz     short RestoreRcx
0x140005f44  retn
0x140005f45  ror     rcx, 10h; StackCookie
0x140005f49  jmp     __report_gsfailure
```
