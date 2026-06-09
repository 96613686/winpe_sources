# __security_check_cookie

- ea: `0x180002620`
- end: `0x18000263e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `105`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800012cc`
- `0x1800015a4`
- `0x180001678`
- `0x18000173c`
- `0x1800017ac`
- `0x18000183c`
- `0x180001ae0`
- `0x180001dd8`
- `0x180001f68`
- `0x18000360c`
- `0x1800038a0`
- `0x1800043f8`
- `0x180004564`
- `0x1800046d0`
- `0x180004a70`
- `0x180004d90`
- `0x180004e50`
- `0x18000527c`
- `0x180005424`
- `0x180005658`
- `0x18000570c`
- `0x180005898`
- `0x180005c94`
- `0x180006090`
- `0x1800063ac`
- `0x1800068b0`
- `0x180006d0c`
- `0x180006d90`
- `0x180006e60`
- `0x180006fd0`
- `0x180007150`
- `0x18000756c`
- `0x180007774`
- `0x18000787c`
- `0x180007ba0`
- `0x180007bf4`
- `0x180007c4c`
- `0x180007ccc`
- `0x180007ddc`
- `0x180007fe8`
- `0x180008898`
- `0x180008994`
- `0x180008c94`
- `0x180008fbc`
- `0x180009100`
- `0x1800092b8`
- `0x180009840`
- `0x180009a48`
- `0x18000a140`

## callees

- `0x180002620`
- `0x180002a00`

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
0x180002620  cmp     rcx, cs:__security_cookie
0x180002627  jnz     short ReportFailure
0x180002629  rol     rcx, 10h
0x18000262d  test    cx, 0FFFFh
0x180002632  jnz     short RestoreRcx
0x180002634  retn
0x180002635  ror     rcx, 10h; StackCookie
0x180002639  jmp     __report_gsfailure
```
