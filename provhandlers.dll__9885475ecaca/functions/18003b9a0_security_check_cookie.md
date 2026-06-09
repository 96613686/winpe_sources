# __security_check_cookie

- ea: `0x18003b9a0`
- end: `0x18003b9be`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `103`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000112c`
- `0x1800011bc`
- `0x180001264`
- `0x180001338`
- `0x180001424`
- `0x180001518`
- `0x180001608`
- `0x180001700`
- `0x1800017c4`
- `0x180001850`
- `0x1800018fc`
- `0x180003d54`
- `0x180004000`
- `0x1800041a4`
- `0x180004d50`
- `0x1800051b0`
- `0x180005ed4`
- `0x180006290`
- `0x18000813c`
- `0x180008ae0`
- `0x180008c40`
- `0x180008ed4`
- `0x18000a59c`
- `0x18000ae44`
- `0x18000b388`
- `0x18000b7f4`
- `0x18000c078`
- `0x18000c26c`
- `0x18000cd7c`
- `0x18000d900`
- `0x18000dd78`
- `0x18000f070`
- `0x180010820`
- `0x1800109a0`
- `0x180010cb4`
- `0x1800114a0`
- `0x180012124`
- `0x1800123b0`
- `0x180012f6c`
- `0x1800145f8`
- `0x180014d68`
- `0x18001504c`
- `0x180015270`
- `0x180015474`
- `0x18001576c`
- `0x180016630`
- `0x180016a28`
- `0x180018630`
- `0x1800186c8`
- `0x180018788`

## callees

- `0x1800028f0`
- `0x18003b9a0`

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
0x18003b9a0  cmp     rcx, cs:__security_cookie
0x18003b9a7  jnz     short ReportFailure
0x18003b9a9  rol     rcx, 10h
0x18003b9ad  test    cx, 0FFFFh
0x18003b9b2  jnz     short RestoreRcx
0x18003b9b4  retn
0x18003b9b5  ror     rcx, 10h
0x18003b9b9  jmp     __report_gsfailure
```
