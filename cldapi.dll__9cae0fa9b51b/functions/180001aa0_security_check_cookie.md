# __security_check_cookie

- ea: `0x180001aa0`
- end: `0x180001abe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `36`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001144`
- `0x180001568`
- `0x180002670`
- `0x180002dc0`
- `0x1800032a0`
- `0x180003d50`
- `0x180004dd0`
- `0x1800064e0`
- `0x1800078d0`
- `0x180007f30`
- `0x1800082b0`
- `0x18000a6b4`
- `0x18000a81c`
- `0x18000a9a0`
- `0x18000ac50`
- `0x18000adb0`
- `0x18000af58`
- `0x18000b0d8`
- `0x18000b248`
- `0x18000b960`
- `0x18000c2a0`
- `0x18000e250`
- `0x18000fea0`
- `0x180010a80`
- `0x180012630`
- `0x180012754`
- `0x180012c28`
- `0x180018564`
- `0x1800192a4`
- `0x180019520`
- `0x180019880`
- `0x180019ed8`
- `0x18001a308`
- `0x18001a694`
- `0x18001c1fc`
- `0x18001cfc4`

## callees

- `0x180001aa0`
- `0x180001fd0`

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
0x180001aa0  cmp     rcx, cs:__security_cookie
0x180001aa7  jnz     short ReportFailure
0x180001aa9  rol     rcx, 10h
0x180001aad  test    cx, 0FFFFh
0x180001ab2  jnz     short RestoreRcx
0x180001ab4  retn
0x180001ab5  ror     rcx, 10h; StackCookie
0x180001ab9  jmp     __report_gsfailure
```
