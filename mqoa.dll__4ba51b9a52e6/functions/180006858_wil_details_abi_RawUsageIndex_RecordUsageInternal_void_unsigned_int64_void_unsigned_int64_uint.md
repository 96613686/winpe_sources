# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180006858`
- end: `0x180006a32`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `474`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180006764`

## callees

- `0x18000400c`
- `0x18000438c`
- `0x180004dc4`
- `0x1800062b0`
- `0x180006858`
- `0x18000746c`
- `0x180007d98`
- `0x180008044`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800069c8`
- `msvcrt!memmove_s` at `0x1800069c8`

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
0x180006858  mov     [rsp-38h+arg_8], rbx
0x18000685d  mov     [rsp-38h+arg_18], r9
0x180006862  push    rbp
0x180006863  push    rsi
0x180006864  push    rdi
0x180006865  push    r12
0x180006867  push    r13
0x180006869  push    r14
0x18000686b  push    r15
0x18000686d  mov     rbp, rsp
0x180006870  sub     rsp, 70h
0x180006874  mov     rdi, [rcx+18h]
0x180006878  mov     r14, r8
0x18000687b  mov     r15, rdx
0x18000687e  mov     rbx, rcx
0x180006881  test    rdi, rdi
0x180006884  jz      loc_180006A18
0x18000688a  movzx   eax, word ptr [rcx+2]
0x18000688e  add     rdi, 0Ah
0x180006892  mov     [rbp+var_40], ax
0x180006896  xorps   xmm0, xmm0
0x180006899  mov     al, [rcx+4]
0x18000689c  mov     [rbp+var_3E], al
0x18000689f  xor     eax, eax
0x1800068a1  mov     [rbp+var_38], ax
0x1800068a5  xor     sil, sil
0x1800068a8  mov     [rbp+arg_0], rdi
0x1800068ac  mov     [rbp+var_3C], 0
0x1800068b3  movdqu  [rbp+var_30], xmm0
0x1800068b8  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800068bc  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x1800068c0  lea     rcx, [rbp+var_40]; this
0x1800068c4  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800068c9  mov     r12d, [rbp+arg_28]
0x1800068cd  mov     r13, [rbp+arg_20]
0x1800068d1  test    al, al
0x1800068d3  jz      short loc_18000693C
0x1800068d5  mov     r8, r14; unsigned __int64
0x1800068d8  lea     rcx, [rbp+var_40]; this
0x1800068dc  mov     rdx, r15; void *
0x1800068df  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x1800068e4  test    eax, eax
0x1800068e6  js      short loc_18000692E
0x1800068e8  mov     r8, [rbp+arg_0]; unsigned __int8 *
0x1800068ec  lea     rdx, [rbp+var_40]; struct wil::details_abi::UsageIndexProperty *
0x1800068f0  mov     rcx, rbx; this
0x1800068f3  jz      short loc_180006903
0x1800068f5  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x1800068fa  mov     rdi, rax
0x1800068fd  mov     [rbp+arg_0], rax
0x180006901  jmp     short loc_1800068B8
0x180006903  mov     r9, [rbp+arg_18]; void *
0x180006907  mov     [rsp+70h+var_48], r12d; unsigned int
0x18000690c  mov     [rsp+70h+var_50], r13; unsigned __int64
0x180006911  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180006916  mov     [rbp+arg_0], rax
0x18000691a  mov     rdi, rax
0x18000691d  test    rax, rax
0x180006920  jnz     short loc_180006929
0x180006922  mov     al, 1
0x180006924  jmp     loc_180006A1A
0x180006929  mov     sil, 1
0x18000692c  jmp     short loc_180006932
0x18000692e  mov     [rbp+arg_0], rdi
0x180006932  xor     r8d, r8d
0x180006935  test    sil, sil
0x180006938  jnz     short loc_180006968
0x18000693a  jmp     short loc_180006944
0x18000693c  mov     rdi, [rbp+arg_0]
0x180006940  mov     [rbx+20h], rdi
0x180006944  lea     rcx, [rbp+var_40]; this
0x180006948  mov     [rbp+var_3C], 1
0x18000694f  mov     [rbp+var_38], r14w
0x180006954  mov     qword ptr [rbp+var_30], 0
0x18000695c  mov     qword ptr [rbp+var_30+8], r15
0x180006960  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180006965  mov     r8, rax
0x180006968  movzx   ecx, word ptr [rbx+6]
0x18000696c  mov     rax, [rbp+arg_18]
0x180006970  mov     [rbp+var_20], cx
0x180006974  mov     cl, [rbx+8]
0x180006977  mov     [rbp+var_1E], cl
0x18000697a  lea     rcx, [rbp+var_20]; this
0x18000697e  mov     [rbp+var_1C], r12d
0x180006982  mov     [rbp+var_18], r13w
0x180006987  mov     [rbp+var_10], 0
0x18000698f  mov     [rbp+var_8], rax
0x180006993  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180006998  mov     rdx, [rbx+28h]
0x18000699c  mov     r9, [rbx+20h]
0x1800069a0  mov     rcx, rdx
0x1800069a3  sub     rcx, r9
0x1800069a6  lea     r14, [rax+r8]
0x1800069aa  cmp     r9, rdx
0x1800069ad  sbb     rax, rax
0x1800069b0  and     rax, rcx
0x1800069b3  cmp     rax, r14
0x1800069b6  jb      short loc_180006A18
0x1800069b8  sub     rdx, r14
0x1800069bb  lea     rcx, [r14+rdi]; Destination
0x1800069bf  sub     rdx, rdi; DestinationSize
0x1800069c2  sub     r9, rdi; SourceSize
0x1800069c5  mov     r8, rdi; Source
0x1800069c8  call    cs:__imp_memmove_s
0x1800069ce  add     [rbx+20h], r14
0x1800069d2  test    sil, sil
0x1800069d5  jnz     short loc_1800069EA
0x1800069d7  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800069db  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x1800069df  lea     rcx, [rbp+var_40]; this
0x1800069e3  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1800069e8  jmp     short loc_1800069FE
0x1800069ea  cmp     [rbp+var_3E], 0
0x1800069ee  jz      short loc_1800069FE
0x1800069f0  mov     edx, [rbp+var_3C]
0x1800069f3  lea     rcx, [rbp+var_40]; this
0x1800069f7  inc     edx; unsigned int
0x1800069f9  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x1800069fe  mov     r8, [rbx+20h]; unsigned __int8 *
0x180006a02  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180006a06  lea     rcx, [rbp+var_20]; this
0x180006a0a  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180006a0f  mov     byte ptr [rbx+38h], 1
0x180006a13  jmp     loc_180006922
0x180006a18  xor     al, al
0x180006a1a  mov     rbx, [rsp+70h+arg_8]
0x180006a22  add     rsp, 70h
0x180006a26  pop     r15
0x180006a28  pop     r14
0x180006a2a  pop     r13
0x180006a2c  pop     r12
0x180006a2e  pop     rdi
0x180006a2f  pop     rsi
0x180006a30  pop     rbp
0x180006a31  retn
```
