# WPP_SF_sd

- ea: `0x180008d7c`
- end: `0x180008de8`
- name: `WPP_SF_sd`
- size: `108`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x1800024e8`
- `0x180002930`
- `0x180003344`
- `0x180003b40`
- `0x180004720`
- `0x1800066c0`
- `0x180007fd0`
- `0x180009948`
- `0x18000adf4`
- `0x18000b134`

## callees

- `0x180008d7c`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x180008ddd`
- `ADVAPI32!TraceMessage` at `0x180008ddd`

## pseudocode

```c
ULONG WPP_SF_sd(TRACEHANDLE a1, USHORT a2, const GUID *a3, const char *a4, ...)
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
0x180008d7c  sub     rsp, 58h
0x180008d80  test    r9, r9
0x180008d83  jz      short loc_180008D98
0x180008d85  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008d89  inc     rax
0x180008d8c  cmp     byte ptr [r9+rax], 0
0x180008d91  jnz     short loc_180008D89
0x180008d93  inc     rax
0x180008d96  jmp     short loc_180008D9D
0x180008d98  mov     eax, 5
0x180008d9d  mov     [rsp+58h+var_18], 0
0x180008da6  lea     r10, aNull; "NULL"
0x180008dad  test    r9, r9
0x180008db0  mov     [rsp+58h+var_20], 4
0x180008db9  cmovz   r9, r10
0x180008dbd  lea     r10, [rsp+58h+arg_20]
0x180008dc5  mov     [rsp+58h+var_28], r10
0x180008dca  mov     [rsp+58h+var_30], rax
0x180008dcf  mov     [rsp+58h+var_38], r9
0x180008dd4  movzx   r9d, dx; MessageNumber
0x180008dd8  mov     edx, 2Bh ; '+'; MessageFlags
0x180008ddd  call    cs:__imp_TraceMessage
0x180008de3  add     rsp, 58h
0x180008de7  retn
```
