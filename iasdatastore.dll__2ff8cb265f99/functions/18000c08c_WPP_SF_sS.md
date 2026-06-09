# WPP_SF_sS

- ea: `0x18000c08c`
- end: `0x18000c10a`
- name: `WPP_SF_sS`
- size: `126`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800093cc`
- `0x180009af8`
- `0x18000a4a0`
- `0x18000b210`

## callees

- `0x18000c08c`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x18000c0ff`
- `ADVAPI32!TraceMessage` at `0x18000c0ff`

## pseudocode

```c
ULONG __fastcall WPP_SF_sS(TRACEHANDLE a1, USHORT a2, __int64 a3, __int64 a4, const wchar_t *a5)
{
  const wchar_t *v5; // r8
  __int64 v6; // rax
  __int64 v7; // rax

  v5 = a5;
  if ( a5 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a5[v6] );
    v7 = 2 * v6 + 2;
  }
  else
  {
    v7 = 10;
  }
  if ( !a5 )
    v5 = L"NULL";
  return TraceMessage(a1, 0x2Bu, &WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids, a2, "NPSDS", 6, v5, v7, 0);
}

```

## disassembly

```asm
0x18000c08c  sub     rsp, 58h
0x18000c090  mov     r8, [rsp+58h+arg_20]
0x18000c098  xor     r10d, r10d
0x18000c09b  test    r8, r8
0x18000c09e  jz      short loc_18000C0B8
0x18000c0a0  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c0a4  inc     rax
0x18000c0a7  cmp     [r8+rax*2], r10w
0x18000c0ac  jnz     short loc_18000C0A4
0x18000c0ae  lea     rax, ds:2[rax*2]
0x18000c0b6  jmp     short loc_18000C0BD
0x18000c0b8  mov     eax, 0Ah
0x18000c0bd  mov     [rsp+58h+var_18], r10
0x18000c0c2  lea     r9, aNull_0; "NULL"
0x18000c0c9  mov     [rsp+58h+var_20], rax
0x18000c0ce  test    r8, r8
0x18000c0d1  lea     rax, aNpsds; "NPSDS"
0x18000c0d8  cmovz   r8, r9
0x18000c0dc  movzx   r9d, dx; MessageNumber
0x18000c0e0  mov     [rsp+58h+var_28], r8
0x18000c0e5  mov     edx, 2Bh ; '+'; MessageFlags
0x18000c0ea  mov     [rsp+58h+var_30], 6
0x18000c0f3  lea     r8, WPP_28e792f4f9d035d6955aea89f2c305fc_Traceguids; MessageGuid
0x18000c0fa  mov     [rsp+58h+var_38], rax
0x18000c0ff  call    cs:__imp_TraceMessage
0x18000c105  add     rsp, 58h
0x18000c109  retn
```
