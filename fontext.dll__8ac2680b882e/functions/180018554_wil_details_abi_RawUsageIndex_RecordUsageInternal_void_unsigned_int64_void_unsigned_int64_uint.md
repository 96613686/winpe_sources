# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180018554`
- end: `0x18001872e`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `474`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180018460`

## callees

- `0x180014fd0`
- `0x180015ff0`
- `0x1800168b0`
- `0x180017fd4`
- `0x180018554`
- `0x180018f30`
- `0x180019a74`
- `0x180019d80`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800186c4`
- `msvcrt!memmove_s` at `0x1800186c4`

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
0x180018554  mov     [rsp-38h+arg_8], rbx
0x180018559  mov     [rsp-38h+arg_18], r9
0x18001855e  push    rbp
0x18001855f  push    rsi
0x180018560  push    rdi
0x180018561  push    r12
0x180018563  push    r13
0x180018565  push    r14
0x180018567  push    r15
0x180018569  mov     rbp, rsp
0x18001856c  sub     rsp, 70h
0x180018570  mov     rdi, [rcx+18h]
0x180018574  mov     r14, r8
0x180018577  mov     r15, rdx
0x18001857a  mov     rbx, rcx
0x18001857d  test    rdi, rdi
0x180018580  jz      loc_180018714
0x180018586  movzx   eax, word ptr [rcx+2]
0x18001858a  add     rdi, 0Ah
0x18001858e  mov     [rbp+var_40], ax
0x180018592  xorps   xmm0, xmm0
0x180018595  mov     al, [rcx+4]
0x180018598  mov     [rbp+var_3E], al
0x18001859b  xor     eax, eax
0x18001859d  mov     [rbp+var_38], ax
0x1800185a1  xor     sil, sil
0x1800185a4  mov     [rbp+arg_0], rdi
0x1800185a8  mov     [rbp+var_3C], 0
0x1800185af  movdqu  [rbp+var_30], xmm0
0x1800185b4  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800185b8  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x1800185bc  lea     rcx, [rbp+var_40]; this
0x1800185c0  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800185c5  mov     r12d, [rbp+arg_28]
0x1800185c9  mov     r13, [rbp+arg_20]
0x1800185cd  test    al, al
0x1800185cf  jz      short loc_180018638
0x1800185d1  mov     r8, r14; unsigned __int64
0x1800185d4  lea     rcx, [rbp+var_40]; this
0x1800185d8  mov     rdx, r15; void *
0x1800185db  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x1800185e0  test    eax, eax
0x1800185e2  js      short loc_18001862A
0x1800185e4  mov     r8, [rbp+arg_0]; unsigned __int8 *
0x1800185e8  lea     rdx, [rbp+var_40]; struct wil::details_abi::UsageIndexProperty *
0x1800185ec  mov     rcx, rbx; this
0x1800185ef  jz      short loc_1800185FF
0x1800185f1  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x1800185f6  mov     rdi, rax
0x1800185f9  mov     [rbp+arg_0], rax
0x1800185fd  jmp     short loc_1800185B4
0x1800185ff  mov     r9, [rbp+arg_18]; void *
0x180018603  mov     [rsp+70h+var_48], r12d; unsigned int
0x180018608  mov     [rsp+70h+var_50], r13; unsigned __int64
0x18001860d  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180018612  mov     [rbp+arg_0], rax
0x180018616  mov     rdi, rax
0x180018619  test    rax, rax
0x18001861c  jnz     short loc_180018625
0x18001861e  mov     al, 1
0x180018620  jmp     loc_180018716
0x180018625  mov     sil, 1
0x180018628  jmp     short loc_18001862E
0x18001862a  mov     [rbp+arg_0], rdi
0x18001862e  xor     r8d, r8d
0x180018631  test    sil, sil
0x180018634  jnz     short loc_180018664
0x180018636  jmp     short loc_180018640
0x180018638  mov     rdi, [rbp+arg_0]
0x18001863c  mov     [rbx+20h], rdi
0x180018640  lea     rcx, [rbp+var_40]; this
0x180018644  mov     [rbp+var_3C], 1
0x18001864b  mov     [rbp+var_38], r14w
0x180018650  mov     qword ptr [rbp+var_30], 0
0x180018658  mov     qword ptr [rbp+var_30+8], r15
0x18001865c  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180018661  mov     r8, rax
0x180018664  movzx   ecx, word ptr [rbx+6]
0x180018668  mov     rax, [rbp+arg_18]
0x18001866c  mov     [rbp+var_20], cx
0x180018670  mov     cl, [rbx+8]
0x180018673  mov     [rbp+var_1E], cl
0x180018676  lea     rcx, [rbp+var_20]; this
0x18001867a  mov     [rbp+var_1C], r12d
0x18001867e  mov     [rbp+var_18], r13w
0x180018683  mov     [rbp+var_10], 0
0x18001868b  mov     [rbp+var_8], rax
0x18001868f  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180018694  mov     rdx, [rbx+28h]
0x180018698  mov     r9, [rbx+20h]
0x18001869c  mov     rcx, rdx
0x18001869f  sub     rcx, r9
0x1800186a2  lea     r14, [rax+r8]
0x1800186a6  cmp     r9, rdx
0x1800186a9  sbb     rax, rax
0x1800186ac  and     rax, rcx
0x1800186af  cmp     rax, r14
0x1800186b2  jb      short loc_180018714
0x1800186b4  sub     rdx, r14
0x1800186b7  lea     rcx, [r14+rdi]; Destination
0x1800186bb  sub     rdx, rdi; DestinationSize
0x1800186be  sub     r9, rdi; SourceSize
0x1800186c1  mov     r8, rdi; Source
0x1800186c4  call    cs:__imp_memmove_s
0x1800186ca  add     [rbx+20h], r14
0x1800186ce  test    sil, sil
0x1800186d1  jnz     short loc_1800186E6
0x1800186d3  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800186d7  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x1800186db  lea     rcx, [rbp+var_40]; this
0x1800186df  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1800186e4  jmp     short loc_1800186FA
0x1800186e6  cmp     [rbp+var_3E], 0
0x1800186ea  jz      short loc_1800186FA
0x1800186ec  mov     edx, [rbp+var_3C]
0x1800186ef  lea     rcx, [rbp+var_40]; this
0x1800186f3  inc     edx; unsigned int
0x1800186f5  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x1800186fa  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800186fe  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180018702  lea     rcx, [rbp+var_20]; this
0x180018706  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18001870b  mov     byte ptr [rbx+38h], 1
0x18001870f  jmp     loc_18001861E
0x180018714  xor     al, al
0x180018716  mov     rbx, [rsp+70h+arg_8]
0x18001871e  add     rsp, 70h
0x180018722  pop     r15
0x180018724  pop     r14
0x180018726  pop     r13
0x180018728  pop     r12
0x18001872a  pop     rdi
0x18001872b  pop     rsi
0x18001872c  pop     rbp
0x18001872d  retn
```
