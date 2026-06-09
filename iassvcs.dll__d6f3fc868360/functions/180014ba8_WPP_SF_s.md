# WPP_SF_s

- ea: `0x180014ba8`
- end: `0x180014bfe`
- name: `WPP_SF_s`
- size: `86`
- prototype: `ULONG __fastcall(TRACEHANDLE, USHORT, const GUID *, const char *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000cad0`
- `0x1800138d0`
- `0x180015304`

## callees

- `0x180014ba8`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x180014bf3`
- `ADVAPI32!TraceMessage` at `0x180014bf3`

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
0x180014ba8  sub     rsp, 48h
0x180014bac  test    r9, r9
0x180014baf  jz      short loc_180014BC4
0x180014bb1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014bb5  inc     rax
0x180014bb8  cmp     byte ptr [r9+rax], 0
0x180014bbd  jnz     short loc_180014BB5
0x180014bbf  inc     rax
0x180014bc2  jmp     short loc_180014BC9
0x180014bc4  mov     eax, 5
0x180014bc9  test    r9, r9
0x180014bcc  mov     [rsp+48h+var_18], 0
0x180014bd5  lea     r10, aNull; "NULL"
0x180014bdc  mov     [rsp+48h+var_20], rax
0x180014be1  cmovz   r9, r10
0x180014be5  mov     [rsp+48h+var_28], r9
0x180014bea  movzx   r9d, dx; MessageNumber
0x180014bee  mov     edx, 2Bh ; '+'; MessageFlags
0x180014bf3  call    cs:__imp_TraceMessage
0x180014bf9  add     rsp, 48h
0x180014bfd  retn
```
