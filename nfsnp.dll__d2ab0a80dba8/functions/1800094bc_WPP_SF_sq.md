# WPP_SF_sq

- ea: `0x1800094bc`
- end: `0x180009528`
- name: `WPP_SF_sq`
- size: `108`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180003344`
- `0x180005c10`
- `0x180005d70`
- `0x180007fd0`
- `0x180009948`

## callees

- `0x1800094bc`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x18000951d`
- `ADVAPI32!TraceMessage` at `0x18000951d`

## pseudocode

```c
ULONG WPP_SF_sq(TRACEHANDLE a1, USHORT a2, const GUID *a3, const char *a4, ...)
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
  return TraceMessage(a1, 0x2Bu, a3, a2, a4, v5, va, 8, 0);
}

```

## disassembly

```asm
0x1800094bc  sub     rsp, 58h
0x1800094c0  test    r9, r9
0x1800094c3  jz      short loc_1800094D8
0x1800094c5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800094c9  inc     rax
0x1800094cc  cmp     byte ptr [r9+rax], 0
0x1800094d1  jnz     short loc_1800094C9
0x1800094d3  inc     rax
0x1800094d6  jmp     short loc_1800094DD
0x1800094d8  mov     eax, 5
0x1800094dd  mov     [rsp+58h+var_18], 0
0x1800094e6  lea     r10, aNull; "NULL"
0x1800094ed  test    r9, r9
0x1800094f0  mov     [rsp+58h+var_20], 8
0x1800094f9  cmovz   r9, r10
0x1800094fd  lea     r10, [rsp+58h+arg_20]
0x180009505  mov     [rsp+58h+var_28], r10
0x18000950a  mov     [rsp+58h+var_30], rax
0x18000950f  mov     [rsp+58h+var_38], r9
0x180009514  movzx   r9d, dx; MessageNumber
0x180009518  mov     edx, 2Bh ; '+'; MessageFlags
0x18000951d  call    cs:__imp_TraceMessage
0x180009523  add     rsp, 58h
0x180009527  retn
```
