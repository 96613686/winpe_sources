# __security_check_cookie

- ea: `0x180015cf0`
- end: `0x180015d0e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `48`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002274`
- `0x1800031dc`
- `0x1800034a8`
- `0x180003794`
- `0x1800039f4`
- `0x180004680`
- `0x180004808`
- `0x180004880`
- `0x180005200`
- `0x18000568c`
- `0x180005838`
- `0x180005b6c`
- `0x18000613c`
- `0x180006354`
- `0x180006724`
- `0x18000701c`
- `0x180007288`
- `0x1800079f8`
- `0x180007c94`
- `0x180008828`
- `0x180008bcc`
- `0x180008fa0`
- `0x180009044`
- `0x1800099e4`
- `0x180009d60`
- `0x18000a9ac`
- `0x18000ac2c`
- `0x18000b500`
- `0x18000c70c`
- `0x18000d100`
- `0x18000d210`
- `0x18000d450`
- `0x18000dfe4`
- `0x18000e3b4`
- `0x18000edb0`
- `0x18000ef60`
- `0x18000f3e4`
- `0x18000f65c`
- `0x18000f784`
- `0x18000f908`
- `0x1800117e0`
- `0x180011cb0`
- `0x180012060`
- `0x180013a08`
- `0x1800146c8`
- `0x180014df8`
- `0x180014ef0`
- `0x180015b60`

## callees

- `0x180001bf0`
- `0x180015cf0`

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
0x180015cf0  cmp     rcx, cs:__security_cookie
0x180015cf7  jnz     short ReportFailure
0x180015cf9  rol     rcx, 10h
0x180015cfd  test    cx, 0FFFFh
0x180015d02  jnz     short RestoreRcx
0x180015d04  retn
0x180015d05  ror     rcx, 10h
0x180015d09  jmp     __report_gsfailure
```
