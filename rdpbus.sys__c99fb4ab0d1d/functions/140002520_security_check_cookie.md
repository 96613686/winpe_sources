# __security_check_cookie

- ea: `0x140002520`
- end: `0x14000253e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001be0`
- `0x140001f10`
- `0x1400023ec`
- `0x140008810`
- `0x140009db8`
- `0x14000a964`

## callees

- `0x140001bd0`
- `0x140002520`

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
0x140002520  cmp     rcx, cs:__security_cookie
0x140002527  jnz     short ReportFailure
0x140002529  rol     rcx, 10h
0x14000252d  test    cx, 0FFFFh
0x140002532  jnz     short RestoreRcx
0x140002534  retn
0x140002535  ror     rcx, 10h; StackCookie
0x140002539  jmp     __report_gsfailure
```
