# WPP_SF_SS

- ea: `0x1800094cc`
- end: `0x18000956f`
- name: `WPP_SF_SS`
- size: `163`
- prototype: `ULONG __fastcall(TRACEHANDLE, USHORT, __int64, const wchar_t *, const wchar_t *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180006f50`
- `0x1800075c4`
- `0x180008900`

## callees

- `0x1800094cc`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x18000955e`
- `ADVAPI32!TraceMessage` at `0x18000955e`

## pseudocode

```c
ULONG __fastcall WPP_SF_SS(TRACEHANDLE a1, USHORT a2, __int64 a3, const wchar_t *a4, const wchar_t *a5)
{
  const wchar_t *v5; // r10
  __int64 v6; // r8
  __int64 v7; // r11
  __int64 v8; // rax
  __int64 v9; // rax
  bool v10; // zf

  v5 = a5;
  v6 = -1;
  v7 = 10;
  if ( a5 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a5[v8] );
    v9 = 2 * v8 + 2;
  }
  else
  {
    v9 = 10;
  }
  if ( !a5 )
    v5 = L"NULL";
  v10 = a4 == 0;
  if ( a4 )
  {
    do
      ++v6;
    while ( a4[v6] );
    v7 = 2 * v6 + 2;
    v10 = a4 == 0;
  }
  if ( v10 )
    a4 = L"NULL";
  return TraceMessage(a1, 0x2Bu, &WPP_8158daeccbd13eff1bb477c819869c69_Traceguids, a2, a4, v7, v5, v9, 0);
}

```

## disassembly

```asm
0x1800094cc  mov     [rsp+arg_0], rbx
0x1800094d1  push    rdi
0x1800094d2  sub     rsp, 50h
0x1800094d6  mov     r10, [rsp+58h+arg_20]
0x1800094de  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800094e2  xor     ebx, ebx
0x1800094e4  mov     r11d, 0Ah
0x1800094ea  test    r10, r10
0x1800094ed  jz      short loc_180009506
0x1800094ef  mov     rax, r8
0x1800094f2  inc     rax
0x1800094f5  cmp     [r10+rax*2], bx
0x1800094fa  jnz     short loc_1800094F2
0x1800094fc  lea     rax, ds:2[rax*2]
0x180009504  jmp     short loc_180009509
0x180009506  mov     rax, r11
0x180009509  test    r10, r10
0x18000950c  lea     rdi, aNull; "NULL"
0x180009513  cmovz   r10, rdi
0x180009517  test    r9, r9
0x18000951a  jz      short loc_180009531
0x18000951c  inc     r8
0x18000951f  cmp     [r9+r8*2], bx
0x180009524  jnz     short loc_18000951C
0x180009526  lea     r11, ds:2[r8*2]
0x18000952e  test    r9, r9
0x180009531  mov     [rsp+58h+var_18], rbx
0x180009536  lea     r8, WPP_8158daeccbd13eff1bb477c819869c69_Traceguids; MessageGuid
0x18000953d  mov     [rsp+58h+var_20], rax
0x180009542  cmovz   r9, rdi
0x180009546  mov     [rsp+58h+var_28], r10
0x18000954b  mov     [rsp+58h+var_30], r11
0x180009550  mov     [rsp+58h+var_38], r9
0x180009555  movzx   r9d, dx; MessageNumber
0x180009559  mov     edx, 2Bh ; '+'; MessageFlags
0x18000955e  call    cs:__imp_TraceMessage
0x180009564  mov     rbx, [rsp+58h+arg_0]
0x180009569  add     rsp, 50h
0x18000956d  pop     rdi
0x18000956e  retn
```
