# __security_check_cookie

- ea: `0x1800292b0`
- end: `0x1800292ce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `89`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001cf4`
- `0x18000272c`
- `0x180002b20`
- `0x180002e20`
- `0x1800030f0`
- `0x1800033d0`
- `0x180003504`
- `0x18000c5e0`
- `0x18000cb80`
- `0x18000d92c`
- `0x18000da3c`
- `0x18000dad8`
- `0x18000dc2c`
- `0x18000de88`
- `0x18000f108`
- `0x18000f810`
- `0x180010330`
- `0x1800108a0`
- `0x180011184`
- `0x180011698`
- `0x1800118f0`
- `0x180012b00`
- `0x1800131f0`
- `0x180013ccc`
- `0x180014240`
- `0x1800144e0`
- `0x180014780`
- `0x180014bc0`
- `0x180014df0`
- `0x1800150f8`
- `0x1800151b4`
- `0x180015370`
- `0x1800158c0`
- `0x180015a94`
- `0x180015e1c`
- `0x180015f58`
- `0x1800161a4`
- `0x1800163f0`
- `0x180016498`
- `0x180016608`
- `0x1800166e0`
- `0x1800167c8`
- `0x180016948`
- `0x180016a74`
- `0x180016b30`
- `0x180016d40`
- `0x1800173a4`
- `0x1800175d8`
- `0x180017740`
- `0x180020a20`

## callees

- `0x180001700`
- `0x1800292b0`

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
0x1800292b0  cmp     rcx, cs:__security_cookie
0x1800292b7  jnz     short ReportFailure
0x1800292b9  rol     rcx, 10h
0x1800292bd  test    cx, 0FFFFh
0x1800292c2  jnz     short RestoreRcx
0x1800292c4  retn
0x1800292c5  ror     rcx, 10h
0x1800292c9  jmp     __report_gsfailure
```
