# __security_check_cookie

- ea: `0x180014ae0`
- end: `0x180014afe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `83`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800017c0`
- `0x18000295c`
- `0x180002d20`
- `0x1800033bc`
- `0x180003570`
- `0x180004260`
- `0x180004580`
- `0x180004718`
- `0x180004800`
- `0x180004c14`
- `0x180005210`
- `0x180005530`
- `0x180005aec`
- `0x180005c00`
- `0x18000663c`
- `0x1800069d8`
- `0x180006afc`
- `0x180006db8`
- `0x180007200`
- `0x180007628`
- `0x180007c0c`
- `0x1800080c4`
- `0x18000829c`
- `0x180008348`
- `0x1800085c8`
- `0x180008c70`
- `0x180009280`
- `0x1800093b0`
- `0x180009464`
- `0x1800097d0`
- `0x1800099a0`
- `0x180009a88`
- `0x180009c30`
- `0x180009e8c`
- `0x18000a1b4`
- `0x18000a3b0`
- `0x18000a66c`
- `0x18000aaf0`
- `0x18000ac40`
- `0x18000af80`
- `0x18000b5f0`
- `0x18000b784`
- `0x18000b850`
- `0x18000b9c0`
- `0x18000c388`
- `0x18000c440`
- `0x18000cfc4`
- `0x18000d208`
- `0x18000d3b4`

## callees

- `0x1800021c0`
- `0x180014ae0`

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
0x180014ae0  cmp     rcx, cs:__security_cookie
0x180014ae7  jnz     short ReportFailure
0x180014ae9  rol     rcx, 10h
0x180014aed  test    cx, 0FFFFh
0x180014af2  jnz     short RestoreRcx
0x180014af4  retn
0x180014af5  ror     rcx, 10h
0x180014af9  jmp     __report_gsfailure
```
