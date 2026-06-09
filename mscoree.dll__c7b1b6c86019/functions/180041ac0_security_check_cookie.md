# __security_check_cookie

- ea: `0x180041ac0`
- end: `0x180041ade`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `118`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001c60`
- `0x180001f20`
- `0x180002710`
- `0x180002a90`
- `0x180003160`
- `0x180003890`
- `0x180003ed0`
- `0x180004230`
- `0x180004660`
- `0x180004ed0`
- `0x180005300`
- `0x180006130`
- `0x180006840`
- `0x180009028`
- `0x180009350`
- `0x180009af4`
- `0x18000a59c`
- `0x18000a884`
- `0x18000aa50`
- `0x18000ac2c`
- `0x18000af8c`
- `0x18000b1f0`
- `0x18000bdf4`
- `0x18000c634`
- `0x18000cedc`
- `0x18000ee54`
- `0x18001099c`
- `0x180010a14`
- `0x1800125ac`
- `0x180012b94`
- `0x180013914`
- `0x1800143f0`
- `0x1800157ac`
- `0x180015c98`
- `0x1800162a8`
- `0x1800171a4`
- `0x180017cb4`
- `0x180017db4`
- `0x1800199f0`
- `0x180019fd0`
- `0x18001a9f8`
- `0x18001abf8`
- `0x18001b808`
- `0x18001c49c`
- `0x18001d1e4`
- `0x18001d888`
- `0x18001e110`
- `0x18001e3c0`
- `0x18001e4c0`
- `0x18001fa30`

## callees

- `0x18000eaa0`
- `0x180041ac0`

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
0x180041ac0  cmp     rcx, cs:__security_cookie
0x180041ac7  jnz     short ReportFailure
0x180041ac9  rol     rcx, 10h
0x180041acd  test    cx, 0FFFFh
0x180041ad2  jnz     short RestoreRcx
0x180041ad4  retn
0x180041ad5  ror     rcx, 10h
0x180041ad9  jmp     __report_gsfailure
```
