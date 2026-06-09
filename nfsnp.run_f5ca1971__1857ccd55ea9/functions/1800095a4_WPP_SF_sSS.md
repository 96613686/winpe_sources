# WPP_SF_sSS

- ea: `0x1800095a4`
- end: `0x18000968e`
- name: `WPP_SF_sSS`
- size: `234`
- prototype: `__int64 __usercall@<rax>(TRACEHANDLE LoggerHandle@<rcx>, __int64, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002a90`
- `0x180004a40`
- `0x180006b50`

## callees

- `0x1800095a4`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x180009678`
- `ADVAPI32!TraceMessage` at `0x180009678`

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
0x1800095a4  push    rbx
0x1800095a6  push    rbp
0x1800095a7  push    rsi
0x1800095a8  push    rdi
0x1800095a9  sub     rsp, 68h
0x1800095ad  mov     r10, [rsp+88h+arg_28]
0x1800095b5  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800095b9  xor     esi, esi
0x1800095bb  movzx   ebx, dx
0x1800095be  mov     rdi, rcx
0x1800095c1  mov     r11d, 0Ah
0x1800095c7  test    r10, r10
0x1800095ca  jz      short loc_1800095E3
0x1800095cc  mov     rax, r8
0x1800095cf  inc     rax
0x1800095d2  cmp     [r10+rax*2], si
0x1800095d7  jnz     short loc_1800095CF
0x1800095d9  lea     rdx, ds:2[rax*2]
0x1800095e1  jmp     short loc_1800095E6
0x1800095e3  mov     rdx, r11
0x1800095e6  mov     rcx, [rsp+88h+arg_20]
0x1800095ee  lea     rbp, aNull_0; "NULL"
0x1800095f5  test    r10, r10
0x1800095f8  cmovz   r10, rbp
0x1800095fc  test    rcx, rcx
0x1800095ff  jz      short loc_180009618
0x180009601  mov     rax, r8
0x180009604  inc     rax
0x180009607  cmp     [rcx+rax*2], si
0x18000960b  jnz     short loc_180009604
0x18000960d  lea     r11, ds:2[rax*2]
0x180009615  test    rcx, rcx
0x180009618  cmovz   rcx, rbp
0x18000961c  test    r9, r9
0x18000961f  jz      short loc_18000962F
0x180009621  inc     r8
0x180009624  cmp     [r9+r8], sil
0x180009628  jnz     short loc_180009621
0x18000962a  inc     r8
0x18000962d  jmp     short loc_180009635
0x18000962f  mov     r8d, 5
0x180009635  mov     [rsp+88h+var_38], rsi
0x18000963a  lea     rax, aNull; "NULL"
0x180009641  mov     [rsp+88h+var_40], rdx
0x180009646  test    r9, r9
0x180009649  mov     [rsp+88h+var_48], r10
0x18000964e  mov     edx, 2Bh ; '+'; MessageFlags
0x180009653  mov     [rsp+88h+var_50], r11
0x180009658  cmovz   r9, rax
0x18000965c  mov     [rsp+88h+var_58], rcx
0x180009661  mov     rcx, rdi; LoggerHandle
0x180009664  mov     [rsp+88h+var_60], r8
0x180009669  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids; MessageGuid
0x180009670  mov     [rsp+88h+var_68], r9
0x180009675  mov     r9d, ebx; MessageNumber
0x180009678  call    cs:__imp_TraceMessage
0x18000967f  nop     dword ptr [rax+rax+00h]
0x180009684  add     rsp, 68h
0x180009688  pop     rdi
0x180009689  pop     rsi
0x18000968a  pop     rbp
0x18000968b  pop     rbx
0x18000968c  retn
```
