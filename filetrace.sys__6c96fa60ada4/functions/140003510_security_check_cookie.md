# __security_check_cookie

- ea: `0x140003510`
- end: `0x14000352e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `9`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400010b0`
- `0x140001ae0`
- `0x140002110`
- `0x140002a00`
- `0x14000336c`
- `0x14000bcd8`
- `0x14000c8b8`
- `0x14000c95c`
- `0x14000e2e0`

## callees

- `0x140001010`
- `0x140003510`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( (PVOID)StackCookie != WmiRegistrationContext.DeviceExtension )
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
0x140003510  cmp     rcx, cs:WmiRegistrationContext.DeviceExtension
0x140003517  jnz     short ReportFailure
0x140003519  rol     rcx, 10h
0x14000351d  test    cx, 0FFFFh
0x140003522  jnz     short RestoreRcx
0x140003524  retn
0x140003525  ror     rcx, 10h; StackCookie
0x140003529  jmp     __report_gsfailure
```
