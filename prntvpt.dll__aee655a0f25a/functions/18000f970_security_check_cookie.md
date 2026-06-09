# __security_check_cookie

- ea: `0x18000f970`
- end: `0x18000f98e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `39`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006344`
- `0x18000ac80`
- `0x18000adb0`
- `0x18000ae80`
- `0x180010b44`
- `0x180010c38`
- `0x18001145c`
- `0x1800115c4`
- `0x1800119c8`
- `0x180012260`
- `0x18001288c`
- `0x180012f34`
- `0x18001324c`
- `0x18001472c`
- `0x180014c64`
- `0x180014fe0`
- `0x1800151dc`
- `0x1800152f0`
- `0x180015464`
- `0x1800155fc`
- `0x1800163c0`
- `0x1800169dc`
- `0x180016ce8`
- `0x1800177a4`
- `0x180017974`
- `0x180017e0c`
- `0x1800180bc`
- `0x180018d70`
- `0x180018f10`
- `0x180019050`
- `0x1800191a0`
- `0x180019300`
- `0x1800194e0`
- `0x1800196c0`
- `0x180019900`
- `0x18001e99c`
- `0x18001eb5c`
- `0x180020bd0`
- `0x1800224c0`

## callees

- `0x18000f970`
- `0x18000f9a0`

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
0x18000f970  cmp     rcx, cs:__security_cookie
0x18000f977  jnz     short ReportFailure
0x18000f979  rol     rcx, 10h
0x18000f97d  test    cx, 0FFFFh
0x18000f982  jnz     short RestoreRcx
0x18000f984  retn
0x18000f985  ror     rcx, 10h; StackCookie
0x18000f989  jmp     __report_gsfailure
```
