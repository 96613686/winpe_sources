# __security_check_cookie

- ea: `0x180013410`
- end: `0x18001342e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `27`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002770`
- `0x180002e20`
- `0x1800034f0`
- `0x180003784`
- `0x180003d40`
- `0x180004110`
- `0x180004664`
- `0x1800049e0`
- `0x180005e44`
- `0x1800061ac`
- `0x180006e20`
- `0x180007e80`
- `0x180009f20`
- `0x18000ac1c`
- `0x18000ef24`
- `0x18000f358`
- `0x18000f464`
- `0x18000fdb0`
- `0x180010720`
- `0x1800108e0`
- `0x180010aa0`
- `0x180010cb0`
- `0x180012588`
- `0x1800127d4`
- `0x180012f48`
- `0x1800130a8`
- `0x180013300`

## callees

- `0x180001f50`
- `0x180013410`

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
0x180013410  cmp     rcx, cs:__security_cookie
0x180013417  jnz     short ReportFailure
0x180013419  rol     rcx, 10h
0x18001341d  test    cx, 0FFFFh
0x180013422  jnz     short RestoreRcx
0x180013424  retn
0x180013425  ror     rcx, 10h
0x180013429  jmp     __report_gsfailure
```
