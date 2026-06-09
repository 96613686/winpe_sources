# WPP_SF_s

- ea: `0x18000daf0`
- end: `0x18000db46`
- name: `WPP_SF_s`
- size: `86`
- prototype: `ULONG __fastcall(TRACEHANDLE, USHORT, const GUID *, const char *)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x1800026a0`
- `0x1800029e0`
- `0x180003190`
- `0x180004e80`
- `0x1800065c0`
- `0x180006dd0`
- `0x180008b30`
- `0x1800093e0`
- `0x18000a148`
- `0x18000a254`
- `0x18000a360`
- `0x18000aa08`
- `0x18000c7b0`

## callees

- `0x18000daf0`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x18000db3b`
- `ADVAPI32!TraceMessage` at `0x18000db3b`

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
0x18000daf0  sub     rsp, 48h
0x18000daf4  test    r9, r9
0x18000daf7  jz      short loc_18000DB0C
0x18000daf9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000dafd  inc     rax
0x18000db00  cmp     byte ptr [r9+rax], 0
0x18000db05  jnz     short loc_18000DAFD
0x18000db07  inc     rax
0x18000db0a  jmp     short loc_18000DB11
0x18000db0c  mov     eax, 5
0x18000db11  test    r9, r9
0x18000db14  mov     [rsp+48h+var_18], 0
0x18000db1d  lea     r10, aNull; "NULL"
0x18000db24  mov     [rsp+48h+var_20], rax
0x18000db29  cmovz   r9, r10
0x18000db2d  mov     [rsp+48h+var_28], r9
0x18000db32  movzx   r9d, dx; MessageNumber
0x18000db36  mov     edx, 2Bh ; '+'; MessageFlags
0x18000db3b  call    cs:__imp_TraceMessage
0x18000db41  add     rsp, 48h
0x18000db45  retn
```
