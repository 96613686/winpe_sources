# WPP_SF_sSS

- ea: `0x180008f28`
- end: `0x18000900b`
- name: `WPP_SF_sSS`
- size: `227`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, __int64, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002930`
- `0x180004720`
- `0x1800066c0`

## callees

- `0x180008f28`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x180008ffc`
- `ADVAPI32!TraceMessage` at `0x180008ffc`

## pseudocode

```c
ULONG __fastcall WPP_SF_sSS(
        TRACEHANDLE LoggerHandle,
        USHORT a2,
        __int64 a3,
        const char *a4,
        const wchar_t *a5,
        const wchar_t *a6)
{
  const wchar_t *v6; // r10
  __int64 v7; // r8
  __int64 v10; // r11
  __int64 v11; // rax
  __int64 v12; // rdx
  const wchar_t *v13; // rcx
  bool v14; // zf
  __int64 v15; // rax
  __int64 v16; // r8

  v6 = a6;
  v7 = -1;
  v10 = 10;
  if ( a6 )
  {
    v11 = -1;
    do
      ++v11;
    while ( a6[v11] );
    v12 = 2 * v11 + 2;
  }
  else
  {
    v12 = 10;
  }
  v13 = a5;
  if ( !a6 )
    v6 = L"NULL";
  v14 = a5 == 0;
  if ( a5 )
  {
    v15 = -1;
    do
      ++v15;
    while ( a5[v15] );
    v10 = 2 * v15 + 2;
    v14 = a5 == 0;
  }
  if ( v14 )
    v13 = L"NULL";
  if ( a4 )
  {
    do
      ++v7;
    while ( a4[v7] );
    v16 = v7 + 1;
  }
  else
  {
    v16 = 5;
  }
  if ( !a4 )
    a4 = "NULL";
  return TraceMessage(
           LoggerHandle,
           0x2Bu,
           &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
           a2,
           a4,
           v16,
           v13,
           v10,
           v6,
           v12,
           0);
}

```

## disassembly

```asm
0x180008f28  push    rbx
0x180008f2a  push    rbp
0x180008f2b  push    rsi
0x180008f2c  push    rdi
0x180008f2d  sub     rsp, 68h
0x180008f31  mov     r10, [rsp+88h+arg_28]
0x180008f39  or      r8, 0FFFFFFFFFFFFFFFFh
0x180008f3d  xor     esi, esi
0x180008f3f  movzx   ebx, dx
0x180008f42  mov     rdi, rcx
0x180008f45  mov     r11d, 0Ah
0x180008f4b  test    r10, r10
0x180008f4e  jz      short loc_180008F67
0x180008f50  mov     rax, r8
0x180008f53  inc     rax
0x180008f56  cmp     [r10+rax*2], si
0x180008f5b  jnz     short loc_180008F53
0x180008f5d  lea     rdx, ds:2[rax*2]
0x180008f65  jmp     short loc_180008F6A
0x180008f67  mov     rdx, r11
0x180008f6a  mov     rcx, [rsp+88h+arg_20]
0x180008f72  lea     rbp, aNull_0; "NULL"
0x180008f79  test    r10, r10
0x180008f7c  cmovz   r10, rbp
0x180008f80  test    rcx, rcx
0x180008f83  jz      short loc_180008F9C
0x180008f85  mov     rax, r8
0x180008f88  inc     rax
0x180008f8b  cmp     [rcx+rax*2], si
0x180008f8f  jnz     short loc_180008F88
0x180008f91  lea     r11, ds:2[rax*2]
0x180008f99  test    rcx, rcx
0x180008f9c  cmovz   rcx, rbp
0x180008fa0  test    r9, r9
0x180008fa3  jz      short loc_180008FB3
0x180008fa5  inc     r8
0x180008fa8  cmp     [r9+r8], sil
0x180008fac  jnz     short loc_180008FA5
0x180008fae  inc     r8
0x180008fb1  jmp     short loc_180008FB9
0x180008fb3  mov     r8d, 5
0x180008fb9  mov     [rsp+88h+var_38], rsi
0x180008fbe  lea     rax, aNull; "NULL"
0x180008fc5  mov     [rsp+88h+var_40], rdx
0x180008fca  test    r9, r9
0x180008fcd  mov     [rsp+88h+var_48], r10
0x180008fd2  mov     edx, 2Bh ; '+'; MessageFlags
0x180008fd7  mov     [rsp+88h+var_50], r11
0x180008fdc  cmovz   r9, rax
0x180008fe0  mov     [rsp+88h+var_58], rcx
0x180008fe5  mov     rcx, rdi; LoggerHandle
0x180008fe8  mov     [rsp+88h+var_60], r8
0x180008fed  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids; MessageGuid
0x180008ff4  mov     [rsp+88h+var_68], r9
0x180008ff9  mov     r9d, ebx; MessageNumber
0x180008ffc  call    cs:__imp_TraceMessage
0x180009002  add     rsp, 68h
0x180009006  pop     rdi
0x180009007  pop     rsi
0x180009008  pop     rbp
0x180009009  pop     rbx
0x18000900a  retn
```
