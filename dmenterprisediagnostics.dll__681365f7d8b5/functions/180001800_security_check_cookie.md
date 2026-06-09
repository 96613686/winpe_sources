# __security_check_cookie

- ea: `0x180001800`
- end: `0x18000181e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `59`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002954`
- `0x180002ad4`
- `0x180002f44`
- `0x180003204`
- `0x180003d2c`
- `0x180003eec`
- `0x1800042b4`
- `0x1800046d4`
- `0x180004aa8`
- `0x180006138`
- `0x180006730`
- `0x180007118`
- `0x1800077b0`
- `0x180008064`
- `0x180008634`
- `0x180008838`
- `0x18000afdc`
- `0x18000b7b0`
- `0x18000bff0`
- `0x18000ca5c`
- `0x18000f760`
- `0x180011618`
- `0x1800123fc`
- `0x18001266c`
- `0x1800127c4`
- `0x1800129cc`
- `0x180014030`
- `0x180014168`
- `0x180014688`
- `0x180015290`
- `0x180015804`
- `0x180016758`
- `0x1800180b0`
- `0x1800195c0`
- `0x18001a090`
- `0x18001a5d0`
- `0x18001b12c`
- `0x18001b184`
- `0x18001b208`
- `0x18001b2ac`
- `0x18001b364`
- `0x18001b570`
- `0x18001b63c`
- `0x18001b77c`
- `0x18001bd94`
- `0x18001d97c`
- `0x18001de90`
- `0x18001f58c`
- `0x18001fd80`
- `0x18001ffe0`

## callees

- `0x180001800`
- `0x180001f00`

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
0x180001800  cmp     rcx, cs:__security_cookie
0x180001807  jnz     short ReportFailure
0x180001809  rol     rcx, 10h
0x18000180d  test    cx, 0FFFFh
0x180001812  jnz     short RestoreRcx
0x180001814  retn
0x180001815  ror     rcx, 10h; StackCookie
0x180001819  jmp     __report_gsfailure
```
