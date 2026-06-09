# WPP_SF_sds

- ea: `0x180008c40`
- end: `0x180008cea`
- name: `WPP_SF_sds`
- size: `170`
- prototype: `ULONG __fastcall(TRACEHANDLE, USHORT, const GUID *, const char *, char, const char *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800075fc`
- `0x18000946c`
- `0x18000a148`

## callees

- `0x180008c40`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x180008cd9`
- `ADVAPI32!TraceMessage` at `0x180008cd9`

## pseudocode

```c
ULONG __fastcall WPP_SF_sds(TRACEHANDLE a1, USHORT a2, const GUID *a3, const char *a4, char a5, const char *a6)
{
  const char *v6; // r11
  __int64 v7; // r10
  __int64 v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rax
  bool v11; // zf

  v6 = a6;
  v7 = -1;
  v8 = 5;
  if ( a6 )
  {
    v9 = -1;
    do
      ++v9;
    while ( a6[v9] );
    v10 = v9 + 1;
  }
  else
  {
    v10 = 5;
  }
  if ( !a6 )
    v6 = "NULL";
  v11 = a4 == 0;
  if ( a4 )
  {
    do
      ++v7;
    while ( a4[v7] );
    v8 = v7 + 1;
    v11 = a4 == 0;
  }
  if ( v11 )
    a4 = "NULL";
  return TraceMessage(a1, 0x2Bu, a3, a2, a4, v8, &a5, 4, v6, v10, 0);
}

```

## disassembly

```asm
0x180008c40  mov     [rsp+arg_0], rbx
0x180008c45  push    rsi
0x180008c46  sub     rsp, 60h
0x180008c4a  mov     r11, [rsp+68h+arg_28]
0x180008c52  or      r10, 0FFFFFFFFFFFFFFFFh
0x180008c56  mov     ebx, 5
0x180008c5b  test    r11, r11
0x180008c5e  jz      short loc_180008C72
0x180008c60  mov     rax, r10
0x180008c63  inc     rax
0x180008c66  cmp     byte ptr [r11+rax], 0
0x180008c6b  jnz     short loc_180008C63
0x180008c6d  inc     rax
0x180008c70  jmp     short loc_180008C75
0x180008c72  mov     rax, rbx
0x180008c75  test    r11, r11
0x180008c78  lea     rsi, aNull; "NULL"
0x180008c7f  cmovz   r11, rsi
0x180008c83  test    r9, r9
0x180008c86  jz      short loc_180008C99
0x180008c88  inc     r10
0x180008c8b  cmp     byte ptr [r9+r10], 0
0x180008c90  jnz     short loc_180008C88
0x180008c92  lea     rbx, [r10+1]
0x180008c96  test    r9, r9
0x180008c99  mov     [rsp+68h+var_18], 0
0x180008ca2  cmovz   r9, rsi
0x180008ca6  mov     [rsp+68h+var_20], rax
0x180008cab  lea     rax, [rsp+68h+arg_20]
0x180008cb3  mov     [rsp+68h+var_28], r11
0x180008cb8  mov     [rsp+68h+var_30], 4
0x180008cc1  mov     [rsp+68h+var_38], rax
0x180008cc6  mov     [rsp+68h+var_40], rbx
0x180008ccb  mov     [rsp+68h+var_48], r9
0x180008cd0  movzx   r9d, dx; MessageNumber
0x180008cd4  mov     edx, 2Bh ; '+'; MessageFlags
0x180008cd9  call    cs:__imp_TraceMessage
0x180008cdf  mov     rbx, [rsp+68h+arg_0]
0x180008ce4  add     rsp, 60h
0x180008ce8  pop     rsi
0x180008ce9  retn
```
