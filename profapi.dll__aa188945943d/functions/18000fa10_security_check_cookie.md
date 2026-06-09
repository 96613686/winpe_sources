# __security_check_cookie

- ea: `0x18000fa10`
- end: `0x18000fa2e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `37`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001300`
- `0x180001360`
- `0x180002ac0`
- `0x180002bb0`
- `0x180003038`
- `0x180003298`
- `0x1800034c0`
- `0x180003914`
- `0x180004230`
- `0x1800060a8`
- `0x180007470`
- `0x1800075e0`
- `0x180007e40`
- `0x180008ce0`
- `0x18000a914`
- `0x18000af04`
- `0x18000b13c`
- `0x18000b3f0`
- `0x18000b56c`
- `0x18000c3c0`
- `0x18000c54c`
- `0x180010e48`
- `0x18001102c`
- `0x180011b70`
- `0x180011e6c`
- `0x180012080`
- `0x1800129b4`
- `0x180014a48`
- `0x180014d54`
- `0x180015b8c`
- `0x180015e0c`
- `0x180016100`
- `0x180016834`
- `0x180016a24`
- `0x180016bec`
- `0x180016f60`

## callees

- `0x18000fa10`
- `0x18000ffd0`

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
0x18000fa10  cmp     rcx, cs:__security_cookie
0x18000fa17  jnz     short ReportFailure
0x18000fa19  rol     rcx, 10h
0x18000fa1d  test    cx, 0FFFFh
0x18000fa22  jnz     short RestoreRcx
0x18000fa24  retn
0x18000fa25  ror     rcx, 10h; StackCookie
0x18000fa29  jmp     __report_gsfailure
```
