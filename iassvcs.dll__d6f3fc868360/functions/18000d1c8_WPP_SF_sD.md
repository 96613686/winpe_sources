# WPP_SF_sD

- ea: `0x18000d1c8`
- end: `0x18000d234`
- name: `WPP_SF_sD`
- size: `108`
- prototype: `ULONG(TRACEHANDLE, USHORT, const GUID *, const char *, ...)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180013b2c`
- `0x180014128`
- `0x180018688`
- `0x180018716`

## callees

- `0x18000d1c8`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x18000d229`
- `ADVAPI32!TraceMessage` at `0x18000d229`

## pseudocode

```c
ULONG WPP_SF_sD(TRACEHANDLE a1, USHORT a2, const GUID *a3, const char *a4, ...)
{
  __int64 v4; // rax
  __int64 v5; // rax
  va_list va; // [rsp+80h] [rbp+28h] BYREF

  va_start(va, a4);
  if ( a4 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a4[v4] );
    v5 = v4 + 1;
  }
  else
  {
    v5 = 5;
  }
  if ( !a4 )
    a4 = "NULL";
  return TraceMessage(a1, 0x2Bu, a3, a2, a4, v5, va, 4, 0);
}

```

## disassembly

```asm
0x18000d1c8  sub     rsp, 58h
0x18000d1cc  test    r9, r9
0x18000d1cf  jz      short loc_18000D1E4
0x18000d1d1  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d1d5  inc     rax
0x18000d1d8  cmp     byte ptr [r9+rax], 0
0x18000d1dd  jnz     short loc_18000D1D5
0x18000d1df  inc     rax
0x18000d1e2  jmp     short loc_18000D1E9
0x18000d1e4  mov     eax, 5
0x18000d1e9  mov     [rsp+58h+var_18], 0
0x18000d1f2  lea     r10, aNull; "NULL"
0x18000d1f9  test    r9, r9
0x18000d1fc  mov     [rsp+58h+var_20], 4
0x18000d205  cmovz   r9, r10
0x18000d209  lea     r10, [rsp+58h+arg_20]
0x18000d211  mov     [rsp+58h+var_28], r10
0x18000d216  mov     [rsp+58h+var_30], rax
0x18000d21b  mov     [rsp+58h+var_38], r9
0x18000d220  movzx   r9d, dx; MessageNumber
0x18000d224  mov     edx, 2Bh ; '+'; MessageFlags
0x18000d229  call    cs:__imp_TraceMessage
0x18000d22f  add     rsp, 58h
0x18000d233  retn
```
