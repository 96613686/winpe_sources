# __security_check_cookie

- ea: `0x1800017b0`
- end: `0x1800017ce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `108`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009be0`
- `0x180009ec0`
- `0x18000b1b0`
- `0x18000b900`
- `0x18000c5d0`
- `0x18000cf80`
- `0x18000d4b0`
- `0x18000d580`
- `0x18000de70`
- `0x18000eb60`
- `0x18000efe0`
- `0x180011860`
- `0x180013110`
- `0x180015a40`
- `0x1800168e0`
- `0x180016f00`
- `0x180017c70`
- `0x1800189a0`
- `0x180019d60`
- `0x18001a6b0`
- `0x18001ab80`
- `0x18001bb60`
- `0x18001cff0`
- `0x18001f1a0`
- `0x18001f800`
- `0x18001ff20`
- `0x180020640`
- `0x180020d30`
- `0x1800213a0`
- `0x180021ab0`
- `0x1800221c0`
- `0x180022330`
- `0x180022470`
- `0x180022820`
- `0x180022bd0`
- `0x180022f00`
- `0x1800232d0`
- `0x1800236a0`
- `0x180023a70`
- `0x180023ed0`
- `0x180024320`
- `0x180024790`
- `0x180024c00`
- `0x180025658`
- `0x180025980`
- `0x180025ccc`
- `0x180025d5c`
- `0x180026bc0`
- `0x1800273c0`
- `0x1800286f0`

## callees

- `0x1800017b0`
- `0x180001d70`

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
0x1800017b0  cmp     rcx, cs:__security_cookie
0x1800017b7  jnz     short ReportFailure
0x1800017b9  rol     rcx, 10h
0x1800017bd  test    cx, 0FFFFh
0x1800017c2  jnz     short RestoreRcx
0x1800017c4  retn
0x1800017c5  ror     rcx, 10h; StackCookie
0x1800017c9  jmp     __report_gsfailure
```
