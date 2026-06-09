# WPP_SF_s

- ea: `0x180003cf0`
- end: `0x180003d46`
- name: `WPP_SF_s`
- size: `86`
- prototype: `ULONG __fastcall(TRACEHANDLE, USHORT, const GUID *, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000327c`
- `0x180006fa8`

## callees

- `0x180003cf0`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x180003d3b`
- `ADVAPI32!TraceMessage` at `0x180003d3b`

## pseudocode

```c
ULONG __fastcall WPP_SF_s(TRACEHANDLE a1, USHORT a2, const GUID *a3, const char *a4)
{
  __int64 v4; // rax
  __int64 v5; // rax

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
  return TraceMessage(a1, 0x2Bu, a3, a2, a4, v5, 0);
}

```

## disassembly

```asm
0x180003cf0  sub     rsp, 48h
0x180003cf4  test    r9, r9
0x180003cf7  jz      short loc_180003D0C
0x180003cf9  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003cfd  inc     rax
0x180003d00  cmp     byte ptr [r9+rax], 0
0x180003d05  jnz     short loc_180003CFD
0x180003d07  inc     rax
0x180003d0a  jmp     short loc_180003D11
0x180003d0c  mov     eax, 5
0x180003d11  test    r9, r9
0x180003d14  mov     [rsp+48h+var_18], 0
0x180003d1d  lea     r10, aNull; "NULL"
0x180003d24  mov     [rsp+48h+var_20], rax
0x180003d29  cmovz   r9, r10
0x180003d2d  mov     [rsp+48h+var_28], r9
0x180003d32  movzx   r9d, dx; MessageNumber
0x180003d36  mov     edx, 2Bh ; '+'; MessageFlags
0x180003d3b  call    cs:__imp_TraceMessage
0x180003d41  add     rsp, 48h
0x180003d45  retn
```
