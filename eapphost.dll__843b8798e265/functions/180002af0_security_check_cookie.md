# __security_check_cookie

- ea: `0x180002af0`
- end: `0x180002b0e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `147`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x18000111c`
- `0x180001304`
- `0x180001528`
- `0x1800015f4`
- `0x1800016e0`
- `0x1800017a8`
- `0x180001870`
- `0x1800019d4`
- `0x180001c88`
- `0x180001f80`
- `0x180004638`
- `0x1800048e8`
- `0x18000529c`
- `0x1800055d0`
- `0x180005774`
- `0x180005d60`
- `0x180007794`
- `0x180007b68`
- `0x1800081a0`
- `0x180009630`
- `0x180009da0`
- `0x18000a040`
- `0x18000a154`
- `0x18000b084`
- `0x18000c60c`
- `0x18000ccb4`
- `0x18000d560`
- `0x18000dd04`
- `0x18000e45c`
- `0x18000e758`
- `0x18000ee98`
- `0x18000fe68`
- `0x18001012c`
- `0x18001024c`
- `0x1800103cc`
- `0x1800105a0`
- `0x180010c0c`
- `0x180010e14`
- `0x1800115b4`
- `0x18001177c`
- `0x180011ae0`
- `0x180011d28`
- `0x1800120c4`
- `0x180012140`
- `0x180012b74`
- `0x180013090`
- `0x180013770`
- `0x180013980`
- `0x180013ee0`

## callees

- `0x180002af0`
- `0x180002f00`

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
0x180002af0  cmp     rcx, cs:__security_cookie
0x180002af7  jnz     short ReportFailure
0x180002af9  rol     rcx, 10h
0x180002afd  test    cx, 0FFFFh
0x180002b02  jnz     short RestoreRcx
0x180002b04  retn
0x180002b05  ror     rcx, 10h; StackCookie
0x180002b09  jmp     __report_gsfailure
```
