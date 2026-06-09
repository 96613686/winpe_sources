# __security_check_cookie

- ea: `0x1800017a0`
- end: `0x1800017be`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `146`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002ad4`
- `0x180002d90`
- `0x180003730`
- `0x180004710`
- `0x1800054d0`
- `0x18000576c`
- `0x1800064fc`
- `0x180006664`
- `0x180006850`
- `0x180006d74`
- `0x180009b0c`
- `0x18000a1e8`
- `0x18000b1e0`
- `0x18000bdc4`
- `0x18000c058`
- `0x18000c710`
- `0x18000d200`
- `0x18000d430`
- `0x18000d6e0`
- `0x18000f2dc`
- `0x18001009c`
- `0x180010328`
- `0x18001043c`
- `0x1800105b0`
- `0x18001075c`
- `0x180010d90`
- `0x180010f84`
- `0x180011d8c`
- `0x180012fdc`
- `0x180013a00`
- `0x180013aac`
- `0x1800140f4`
- `0x1800141b0`
- `0x180014f20`
- `0x180015fc4`
- `0x180016400`
- `0x18001647c`
- `0x180016518`
- `0x180016ec0`
- `0x18001729c`
- `0x18001783c`
- `0x180017ea0`
- `0x1800182b0`
- `0x1800188e0`
- `0x180019320`
- `0x1800197a0`
- `0x180019a70`
- `0x18001a090`
- `0x18001a390`
- `0x18001a720`

## callees

- `0x1800017a0`
- `0x180001d60`

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
0x1800017a0  cmp     rcx, cs:__security_cookie
0x1800017a7  jnz     short ReportFailure
0x1800017a9  rol     rcx, 10h
0x1800017ad  test    cx, 0FFFFh
0x1800017b2  jnz     short RestoreRcx
0x1800017b4  retn
0x1800017b5  ror     rcx, 10h; StackCookie
0x1800017b9  jmp     __report_gsfailure
```
