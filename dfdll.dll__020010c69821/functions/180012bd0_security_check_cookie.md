# __security_check_cookie

- ea: `0x180012bd0`
- end: `0x180012bee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `35`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800013cc`
- `0x180003168`
- `0x18000444c`
- `0x180004580`
- `0x180004bcc`
- `0x180004cfc`
- `0x180006180`
- `0x180006e60`
- `0x180007040`
- `0x180007130`
- `0x18000949c`
- `0x18000972c`
- `0x180009c44`
- `0x180009e0c`
- `0x18000a2ac`
- `0x180010f34`
- `0x180011ba8`
- `0x180012b58`
- `0x180013a70`
- `0x180015204`
- `0x180015700`
- `0x1800165e0`
- `0x180019244`
- `0x180019980`
- `0x180019f5c`
- `0x18001a3e8`
- `0x18001bae0`
- `0x18001bee8`
- `0x18001c028`
- `0x18001c1dc`
- `0x18001d124`
- `0x18001d32c`
- `0x18001d434`
- `0x18001d550`
- `0x18001e360`

## callees

- `0x180012bd0`
- `0x180013310`

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
0x180012bd0  cmp     rcx, cs:__security_cookie
0x180012bd7  jnz     short ReportFailure
0x180012bd9  rol     rcx, 10h
0x180012bdd  test    cx, 0FFFFh
0x180012be2  jnz     short RestoreRcx
0x180012be4  retn
0x180012be5  ror     rcx, 10h
0x180012be9  jmp     __report_gsfailure
```
