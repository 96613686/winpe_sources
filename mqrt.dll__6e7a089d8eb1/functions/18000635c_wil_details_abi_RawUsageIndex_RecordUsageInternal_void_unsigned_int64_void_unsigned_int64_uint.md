# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18000635c`
- end: `0x180006536`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `474`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180006268`

## callees

- `0x180003fdc`
- `0x1800042a8`
- `0x180004b70`
- `0x180005dfc`
- `0x18000635c`
- `0x180006e9c`
- `0x180007730`
- `0x180007aa8`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800064cc`
- `msvcrt!memmove_s` at `0x1800064cc`

## pseudocode

```c
char __fastcall wil::details_abi::RawUsageIndex::RecordUsageInternal(
        wil::details_abi::RawUsageIndex *this,
        void *a2,
        unsigned __int64 a3,
        void *a4,
        unsigned __int64 a5,
        unsigned int a6)
{
  __int64 v6; // rdi
  unsigned __int8 *v10; // rdi
  char v11; // si
  bool v12; // al
  unsigned int v13; // r12d
  unsigned __int64 v14; // r13
  int v15; // eax
  unsigned __int64 Size; // rax
  unsigned __int64 v18; // rdx
  unsigned __int64 v19; // r9
  __int64 v20; // r8
  __int64 v21; // r14
  __int16 v22; // [rsp+30h] [rbp-40h] BYREF
  char v23; // [rsp+32h] [rbp-3Eh]
  int v24; // [rsp+34h] [rbp-3Ch]
  __int16 v25; // [rsp+38h] [rbp-38h]
  __int128 v26; // [rsp+40h] [rbp-30h]
  __int16 v27; // [rsp+50h] [rbp-20h] BYREF
  char v28; // [rsp+52h] [rbp-1Eh]
  unsigned int v29; // [rsp+54h] [rbp-1Ch]
  __int16 v30; // [rsp+58h] [rbp-18h]
  __int64 v31; // [rsp+60h] [rbp-10h]
  void *v32; // [rsp+68h] [rbp-8h]
  unsigned __int8 *InsertionPointOrIncrement; // [rsp+B0h] [rbp+40h] BYREF
  void *v34; // [rsp+C8h] [rbp+58h]

  v34 = a4;
  v6 = *((_QWORD *)this + 3);
  if ( v6 )
  {
    v10 = (unsigned __int8 *)(v6 + 10);
    v22 = *((_WORD *)this + 1);
    v23 = *((_BYTE *)this + 4);
    v25 = 0;
    v11 = 0;
    InsertionPointOrIncrement = v10;
    v24 = 0;
    v26 = 0;
    while ( 1 )
    {
      v12 = wil::details_abi::UsageIndexProperty::Read(
              (wil::details_abi::UsageIndexProperty *)&v22,
              &InsertionPointOrIncrement,
              *((unsigned __int8 **)this + 4));
      v13 = a6;
      v14 = a5;
      if ( !v12 )
      {
        v10 = InsertionPointOrIncrement;
        *((_QWORD *)this + 4) = InsertionPointOrIncrement;
        goto LABEL_14;
      }
      v15 = wil::details_abi::UsageIndexProperty::Compare((wil::details_abi::UsageIndexProperty *)&v22, a2, a3);
      if ( v15 < 0 )
      {
        InsertionPointOrIncrement = v10;
        goto LABEL_11;
      }
      if ( !v15 )
        break;
      v10 = wil::details_abi::RawUsageIndex::SkipValues(
              this,
              (struct wil::details_abi::UsageIndexProperty *)&v22,
              InsertionPointOrIncrement);
      InsertionPointOrIncrement = v10;
    }
    InsertionPointOrIncrement = wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(
                                  this,
                                  (struct wil::details_abi::UsageIndexProperty *)&v22,
                                  InsertionPointOrIncrement,
                                  v34,
                                  v14,
                                  v13);
    v10 = InsertionPointOrIncrement;
    if ( !InsertionPointOrIncrement )
      return 1;
    v11 = 1;
LABEL_11:
    if ( v11 )
      goto LABEL_15;
LABEL_14:
    v24 = 1;
    v25 = a3;
    *(_QWORD *)&v26 = 0;
    *((_QWORD *)&v26 + 1) = a2;
    wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v22);
LABEL_15:
    v27 = *((_WORD *)this + 3);
    v28 = *((_BYTE *)this + 8);
    v29 = v13;
    v30 = v14;
    v31 = 0;
    v32 = v34;
    Size = wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v27);
    v18 = *((_QWORD *)this + 5);
    v19 = *((_QWORD *)this + 4);
    v21 = Size + v20;
    if ( ((v18 - v19) & -(__int64)(v19 < v18)) >= Size + v20 )
    {
      memmove_s(&v10[v21], v18 - v21 - (_QWORD)v10, v10, v19 - (_QWORD)v10);
      *((_QWORD *)this + 4) += v21;
      if ( v11 )
      {
        if ( v23 )
          wil::details_abi::UsageIndexProperty::UpdateCount((wil::details_abi::UsageIndexProperty *)&v22, v24 + 1);
      }
      else
      {
        wil::details_abi::UsageIndexProperty::Write(
          (wil::details_abi::UsageIndexProperty *)&v22,
          &InsertionPointOrIncrement,
          *((unsigned __int8 **)this + 4));
      }
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v27,
        &InsertionPointOrIncrement,
        *((unsigned __int8 **)this + 4));
      *((_BYTE *)this + 56) = 1;
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000635c  mov     [rsp-38h+arg_8], rbx
0x180006361  mov     [rsp-38h+arg_18], r9
0x180006366  push    rbp
0x180006367  push    rsi
0x180006368  push    rdi
0x180006369  push    r12
0x18000636b  push    r13
0x18000636d  push    r14
0x18000636f  push    r15
0x180006371  mov     rbp, rsp
0x180006374  sub     rsp, 70h
0x180006378  mov     rdi, [rcx+18h]
0x18000637c  mov     r14, r8
0x18000637f  mov     r15, rdx
0x180006382  mov     rbx, rcx
0x180006385  test    rdi, rdi
0x180006388  jz      loc_18000651C
0x18000638e  movzx   eax, word ptr [rcx+2]
0x180006392  add     rdi, 0Ah
0x180006396  mov     [rbp+var_40], ax
0x18000639a  xorps   xmm0, xmm0
0x18000639d  mov     al, [rcx+4]
0x1800063a0  mov     [rbp+var_3E], al
0x1800063a3  xor     eax, eax
0x1800063a5  mov     [rbp+var_38], ax
0x1800063a9  xor     sil, sil
0x1800063ac  mov     [rbp+arg_0], rdi
0x1800063b0  mov     [rbp+var_3C], 0
0x1800063b7  movdqu  [rbp+var_30], xmm0
0x1800063bc  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800063c0  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x1800063c4  lea     rcx, [rbp+var_40]; this
0x1800063c8  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800063cd  mov     r12d, [rbp+arg_28]
0x1800063d1  mov     r13, [rbp+arg_20]
0x1800063d5  test    al, al
0x1800063d7  jz      short loc_180006440
0x1800063d9  mov     r8, r14; unsigned __int64
0x1800063dc  lea     rcx, [rbp+var_40]; this
0x1800063e0  mov     rdx, r15; void *
0x1800063e3  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x1800063e8  test    eax, eax
0x1800063ea  js      short loc_180006432
0x1800063ec  mov     r8, [rbp+arg_0]; unsigned __int8 *
0x1800063f0  lea     rdx, [rbp+var_40]; struct wil::details_abi::UsageIndexProperty *
0x1800063f4  mov     rcx, rbx; this
0x1800063f7  jz      short loc_180006407
0x1800063f9  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x1800063fe  mov     rdi, rax
0x180006401  mov     [rbp+arg_0], rax
0x180006405  jmp     short loc_1800063BC
0x180006407  mov     r9, [rbp+arg_18]; void *
0x18000640b  mov     [rsp+70h+var_48], r12d; unsigned int
0x180006410  mov     [rsp+70h+var_50], r13; unsigned __int64
0x180006415  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18000641a  mov     [rbp+arg_0], rax
0x18000641e  mov     rdi, rax
0x180006421  test    rax, rax
0x180006424  jnz     short loc_18000642D
0x180006426  mov     al, 1
0x180006428  jmp     loc_18000651E
0x18000642d  mov     sil, 1
0x180006430  jmp     short loc_180006436
0x180006432  mov     [rbp+arg_0], rdi
0x180006436  xor     r8d, r8d
0x180006439  test    sil, sil
0x18000643c  jnz     short loc_18000646C
0x18000643e  jmp     short loc_180006448
0x180006440  mov     rdi, [rbp+arg_0]
0x180006444  mov     [rbx+20h], rdi
0x180006448  lea     rcx, [rbp+var_40]; this
0x18000644c  mov     [rbp+var_3C], 1
0x180006453  mov     [rbp+var_38], r14w
0x180006458  mov     qword ptr [rbp+var_30], 0
0x180006460  mov     qword ptr [rbp+var_30+8], r15
0x180006464  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180006469  mov     r8, rax
0x18000646c  movzx   ecx, word ptr [rbx+6]
0x180006470  mov     rax, [rbp+arg_18]
0x180006474  mov     [rbp+var_20], cx
0x180006478  mov     cl, [rbx+8]
0x18000647b  mov     [rbp+var_1E], cl
0x18000647e  lea     rcx, [rbp+var_20]; this
0x180006482  mov     [rbp+var_1C], r12d
0x180006486  mov     [rbp+var_18], r13w
0x18000648b  mov     [rbp+var_10], 0
0x180006493  mov     [rbp+var_8], rax
0x180006497  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18000649c  mov     rdx, [rbx+28h]
0x1800064a0  mov     r9, [rbx+20h]
0x1800064a4  mov     rcx, rdx
0x1800064a7  sub     rcx, r9
0x1800064aa  lea     r14, [rax+r8]
0x1800064ae  cmp     r9, rdx
0x1800064b1  sbb     rax, rax
0x1800064b4  and     rax, rcx
0x1800064b7  cmp     rax, r14
0x1800064ba  jb      short loc_18000651C
0x1800064bc  sub     rdx, r14
0x1800064bf  lea     rcx, [r14+rdi]; Destination
0x1800064c3  sub     rdx, rdi; DestinationSize
0x1800064c6  sub     r9, rdi; SourceSize
0x1800064c9  mov     r8, rdi; Source
0x1800064cc  call    cs:__imp_memmove_s
0x1800064d2  add     [rbx+20h], r14
0x1800064d6  test    sil, sil
0x1800064d9  jnz     short loc_1800064EE
0x1800064db  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800064df  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x1800064e3  lea     rcx, [rbp+var_40]; this
0x1800064e7  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1800064ec  jmp     short loc_180006502
0x1800064ee  cmp     [rbp+var_3E], 0
0x1800064f2  jz      short loc_180006502
0x1800064f4  mov     edx, [rbp+var_3C]
0x1800064f7  lea     rcx, [rbp+var_40]; this
0x1800064fb  inc     edx; unsigned int
0x1800064fd  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x180006502  mov     r8, [rbx+20h]; unsigned __int8 *
0x180006506  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x18000650a  lea     rcx, [rbp+var_20]; this
0x18000650e  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180006513  mov     byte ptr [rbx+38h], 1
0x180006517  jmp     loc_180006426
0x18000651c  xor     al, al
0x18000651e  mov     rbx, [rsp+70h+arg_8]
0x180006526  add     rsp, 70h
0x18000652a  pop     r15
0x18000652c  pop     r14
0x18000652e  pop     r13
0x180006530  pop     r12
0x180006532  pop     rdi
0x180006533  pop     rsi
0x180006534  pop     rbp
0x180006535  retn
```
