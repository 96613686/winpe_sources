# __security_check_cookie

- ea: `0x180001640`
- end: `0x18000165e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `41`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800021f0`
- `0x180003740`
- `0x18000690c`
- `0x180006cc0`
- `0x180007134`
- `0x1800073e0`
- `0x1800080dc`
- `0x180008248`
- `0x180008414`
- `0x180008b54`
- `0x180008f08`
- `0x18000a580`
- `0x18000acac`
- `0x18000bd7c`
- `0x18000cbf0`
- `0x18000cdd8`
- `0x18000d0cc`
- `0x18000d3c0`
- `0x18000d6a4`
- `0x18000e1f4`
- `0x18000eb94`
- `0x18000f19c`
- `0x18000f254`
- `0x18000f670`
- `0x18000faf0`
- `0x18000fcb8`
- `0x180011128`
- `0x180012d98`
- `0x180012e34`
- `0x180012ef0`
- `0x180013408`
- `0x180013b48`
- `0x180013de4`
- `0x180015fb8`
- `0x180016054`
- `0x180017018`
- `0x18001711c`
- `0x18001b378`
- `0x18001b620`
- `0x18001c314`
- `0x180021cb0`

## callees

- `0x180001640`
- `0x180001bd0`

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
0x180001640  cmp     rcx, cs:__security_cookie
0x180001647  jnz     short ReportFailure
0x180001649  rol     rcx, 10h
0x18000164d  test    cx, 0FFFFh
0x180001652  jnz     short RestoreRcx
0x180001654  retn
0x180001655  ror     rcx, 10h; StackCookie
0x180001659  jmp     __report_gsfailure
```
