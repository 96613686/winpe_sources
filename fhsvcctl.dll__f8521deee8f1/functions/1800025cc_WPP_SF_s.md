# WPP_SF_s

- ea: `0x1800025cc`
- end: `0x180002622`
- name: `WPP_SF_s`
- size: `86`
- prototype: `ULONG __fastcall(TRACEHANDLE, USHORT, const GUID *, const char *)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x1800022f0`
- `0x1800029d0`
- `0x180002b50`
- `0x180002c40`
- `0x180002db0`
- `0x180002f90`
- `0x180003070`
- `0x180003150`
- `0x180003230`
- `0x180003610`
- `0x180003700`
- `0x1800037f0`
- `0x1800038e0`

## callees

- `0x1800025cc`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x180002617`
- `ADVAPI32!TraceMessage` at `0x180002617`

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
0x1800025cc  sub     rsp, 48h
0x1800025d0  test    r9, r9
0x1800025d3  jz      short loc_1800025E8
0x1800025d5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800025d9  inc     rax
0x1800025dc  cmp     byte ptr [r9+rax], 0
0x1800025e1  jnz     short loc_1800025D9
0x1800025e3  inc     rax
0x1800025e6  jmp     short loc_1800025ED
0x1800025e8  mov     eax, 5
0x1800025ed  test    r9, r9
0x1800025f0  mov     [rsp+48h+var_18], 0
0x1800025f9  lea     r10, aNull; "NULL"
0x180002600  mov     [rsp+48h+var_20], rax
0x180002605  cmovz   r9, r10
0x180002609  mov     [rsp+48h+var_28], r9
0x18000260e  movzx   r9d, dx; MessageNumber
0x180002612  mov     edx, 2Bh ; '+'; MessageFlags
0x180002617  call    cs:__imp_TraceMessage
0x18000261d  add     rsp, 48h
0x180002621  retn
```
