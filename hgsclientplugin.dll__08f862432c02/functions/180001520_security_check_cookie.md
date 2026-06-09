# __security_check_cookie

- ea: `0x180001520`
- end: `0x18000153e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `30`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800025f4`
- `0x1800028a0`
- `0x180002e48`
- `0x180003218`
- `0x180003784`
- `0x180003b00`
- `0x18000545c`
- `0x180005920`
- `0x180006060`
- `0x1800065c0`
- `0x1800068ec`
- `0x1800069fc`
- `0x180006b00`
- `0x180006e90`
- `0x180007080`
- `0x180007234`
- `0x180007bd0`
- `0x180007c80`
- `0x180007f80`
- `0x1800085ec`
- `0x1800088cc`
- `0x180008d18`
- `0x180008ecc`
- `0x180009070`
- `0x1800092fc`
- `0x1800096ec`
- `0x180009aa4`
- `0x180009e50`
- `0x18000a070`
- `0x18000a768`

## callees

- `0x180001520`
- `0x180001b60`

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
0x180001520  cmp     rcx, cs:__security_cookie
0x180001527  jnz     short ReportFailure
0x180001529  rol     rcx, 10h
0x18000152d  test    cx, 0FFFFh
0x180001532  jnz     short RestoreRcx
0x180001534  retn
0x180001535  ror     rcx, 10h; StackCookie
0x180001539  jmp     __report_gsfailure
```
