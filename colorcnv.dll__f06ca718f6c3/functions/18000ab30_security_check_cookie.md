# __security_check_cookie

- ea: `0x18000ab30`
- end: `0x18000ab4e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `25`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002ee0`
- `0x180005300`
- `0x180005ba0`
- `0x180005d58`
- `0x18000940c`
- `0x180009854`
- `0x180009bf8`
- `0x180009ea8`
- `0x180009fc0`
- `0x18000a0ec`
- `0x18000c3ec`
- `0x18000d890`
- `0x18000da60`
- `0x18000eab0`
- `0x18000eb80`
- `0x18000ebf8`
- `0x18000eef0`
- `0x18000f530`
- `0x18000f7cc`
- `0x18000fb50`
- `0x18000ff14`
- `0x180010254`
- `0x180010608`
- `0x180013b68`
- `0x180029eec`

## callees

- `0x18000ab30`
- `0x18000b0c0`

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
0x18000ab30  cmp     rcx, cs:__security_cookie
0x18000ab37  jnz     short ReportFailure
0x18000ab39  rol     rcx, 10h
0x18000ab3d  test    cx, 0FFFFh
0x18000ab42  jnz     short RestoreRcx
0x18000ab44  retn
0x18000ab45  ror     rcx, 10h; StackCookie
0x18000ab49  jmp     __report_gsfailure
```
