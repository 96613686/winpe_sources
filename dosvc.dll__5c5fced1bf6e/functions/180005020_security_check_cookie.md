# __security_check_cookie

- ea: `0x180005020`
- end: `0x18000503e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `27`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800010f0`
- `0x180001170`
- `0x180001380`
- `0x180001790`
- `0x180001a70`
- `0x180001c20`
- `0x180001f60`
- `0x180002670`
- `0x180003030`
- `0x180003448`
- `0x1800035b0`
- `0x1800042a4`
- `0x180004764`
- `0x1800054c4`
- `0x180006280`
- `0x180006858`
- `0x180006a34`
- `0x180006dd4`
- `0x1800070b8`
- `0x180008138`
- `0x180008610`
- `0x1800087c0`
- `0x180009608`
- `0x180009824`
- `0x1800099a8`
- `0x180009d00`
- `0x180009fb8`

## callees

- `0x180005020`
- `0x1800056f0`

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
0x180005020  cmp     rcx, cs:__security_cookie
0x180005027  jnz     short ReportFailure
0x180005029  rol     rcx, 10h
0x18000502d  test    cx, 0FFFFh
0x180005032  jnz     short RestoreRcx
0x180005034  retn
0x180005035  ror     rcx, 10h; StackCookie
0x180005039  jmp     __report_gsfailure
```
