# __security_check_cookie

- ea: `0x18000c030`
- end: `0x18000c04e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `22`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001430`
- `0x180001870`
- `0x180001bd0`
- `0x180001fd0`
- `0x180002210`
- `0x180002ca0`
- `0x180002f7c`
- `0x180003110`
- `0x180003560`
- `0x180004790`
- `0x180004bf0`
- `0x1800054f0`
- `0x1800068a0`
- `0x180007200`
- `0x1800085e0`
- `0x180008764`
- `0x180008bbc`
- `0x180008c40`
- `0x1800092ac`
- `0x18000b8dc`
- `0x18000bf00`

## callees

- `0x180007d40`
- `0x18000c030`

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
0x18000c030  cmp     rcx, cs:__security_cookie
0x18000c037  jnz     short ReportFailure
0x18000c039  rol     rcx, 10h
0x18000c03d  test    cx, 0FFFFh
0x18000c042  jnz     short RestoreRcx
0x18000c044  retn
0x18000c045  ror     rcx, 10h
0x18000c049  jmp     __report_gsfailure
```
