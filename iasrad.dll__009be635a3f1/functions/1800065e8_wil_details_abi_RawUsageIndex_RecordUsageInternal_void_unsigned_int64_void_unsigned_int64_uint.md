# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x1800065e8`
- end: `0x1800067c2`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `474`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800064f4`

## callees

- `0x180003c04`
- `0x180003fb8`
- `0x180004768`
- `0x180005fc8`
- `0x1800065e8`
- `0x180007684`
- `0x180007fdc`
- `0x18000839c`

## import_xrefs

- `msvcrt!memmove_s` at `0x180006758`
- `msvcrt!memmove_s` at `0x180006758`

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
0x1800065e8  mov     [rsp-38h+arg_8], rbx
0x1800065ed  mov     [rsp-38h+arg_18], r9
0x1800065f2  push    rbp
0x1800065f3  push    rsi
0x1800065f4  push    rdi
0x1800065f5  push    r12
0x1800065f7  push    r13
0x1800065f9  push    r14
0x1800065fb  push    r15
0x1800065fd  mov     rbp, rsp
0x180006600  sub     rsp, 70h
0x180006604  mov     rdi, [rcx+18h]
0x180006608  mov     r14, r8
0x18000660b  mov     r15, rdx
0x18000660e  mov     rbx, rcx
0x180006611  test    rdi, rdi
0x180006614  jz      loc_1800067A8
0x18000661a  movzx   eax, word ptr [rcx+2]
0x18000661e  add     rdi, 0Ah
0x180006622  mov     [rbp+var_40], ax
0x180006626  xorps   xmm0, xmm0
0x180006629  mov     al, [rcx+4]
0x18000662c  mov     [rbp+var_3E], al
0x18000662f  xor     eax, eax
0x180006631  mov     [rbp+var_38], ax
0x180006635  xor     sil, sil
0x180006638  mov     [rbp+arg_0], rdi
0x18000663c  mov     [rbp+var_3C], 0
0x180006643  movdqu  [rbp+var_30], xmm0
0x180006648  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000664c  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180006650  lea     rcx, [rbp+var_40]; this
0x180006654  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180006659  mov     r12d, [rbp+arg_28]
0x18000665d  mov     r13, [rbp+arg_20]
0x180006661  test    al, al
0x180006663  jz      short loc_1800066CC
0x180006665  mov     r8, r14; unsigned __int64
0x180006668  lea     rcx, [rbp+var_40]; this
0x18000666c  mov     rdx, r15; void *
0x18000666f  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x180006674  test    eax, eax
0x180006676  js      short loc_1800066BE
0x180006678  mov     r8, [rbp+arg_0]; unsigned __int8 *
0x18000667c  lea     rdx, [rbp+var_40]; struct wil::details_abi::UsageIndexProperty *
0x180006680  mov     rcx, rbx; this
0x180006683  jz      short loc_180006693
0x180006685  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x18000668a  mov     rdi, rax
0x18000668d  mov     [rbp+arg_0], rax
0x180006691  jmp     short loc_180006648
0x180006693  mov     r9, [rbp+arg_18]; void *
0x180006697  mov     [rsp+70h+var_48], r12d; unsigned int
0x18000669c  mov     [rsp+70h+var_50], r13; unsigned __int64
0x1800066a1  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x1800066a6  mov     [rbp+arg_0], rax
0x1800066aa  mov     rdi, rax
0x1800066ad  test    rax, rax
0x1800066b0  jnz     short loc_1800066B9
0x1800066b2  mov     al, 1
0x1800066b4  jmp     loc_1800067AA
0x1800066b9  mov     sil, 1
0x1800066bc  jmp     short loc_1800066C2
0x1800066be  mov     [rbp+arg_0], rdi
0x1800066c2  xor     r8d, r8d
0x1800066c5  test    sil, sil
0x1800066c8  jnz     short loc_1800066F8
0x1800066ca  jmp     short loc_1800066D4
0x1800066cc  mov     rdi, [rbp+arg_0]
0x1800066d0  mov     [rbx+20h], rdi
0x1800066d4  lea     rcx, [rbp+var_40]; this
0x1800066d8  mov     [rbp+var_3C], 1
0x1800066df  mov     [rbp+var_38], r14w
0x1800066e4  mov     qword ptr [rbp+var_30], 0
0x1800066ec  mov     qword ptr [rbp+var_30+8], r15
0x1800066f0  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x1800066f5  mov     r8, rax
0x1800066f8  movzx   ecx, word ptr [rbx+6]
0x1800066fc  mov     rax, [rbp+arg_18]
0x180006700  mov     [rbp+var_20], cx
0x180006704  mov     cl, [rbx+8]
0x180006707  mov     [rbp+var_1E], cl
0x18000670a  lea     rcx, [rbp+var_20]; this
0x18000670e  mov     [rbp+var_1C], r12d
0x180006712  mov     [rbp+var_18], r13w
0x180006717  mov     [rbp+var_10], 0
0x18000671f  mov     [rbp+var_8], rax
0x180006723  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180006728  mov     rdx, [rbx+28h]
0x18000672c  mov     r9, [rbx+20h]
0x180006730  mov     rcx, rdx
0x180006733  sub     rcx, r9
0x180006736  lea     r14, [rax+r8]
0x18000673a  cmp     r9, rdx
0x18000673d  sbb     rax, rax
0x180006740  and     rax, rcx
0x180006743  cmp     rax, r14
0x180006746  jb      short loc_1800067A8
0x180006748  sub     rdx, r14
0x18000674b  lea     rcx, [r14+rdi]; Destination
0x18000674f  sub     rdx, rdi; DestinationSize
0x180006752  sub     r9, rdi; SourceSize
0x180006755  mov     r8, rdi; Source
0x180006758  call    cs:__imp_memmove_s
0x18000675e  add     [rbx+20h], r14
0x180006762  test    sil, sil
0x180006765  jnz     short loc_18000677A
0x180006767  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000676b  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x18000676f  lea     rcx, [rbp+var_40]; this
0x180006773  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180006778  jmp     short loc_18000678E
0x18000677a  cmp     [rbp+var_3E], 0
0x18000677e  jz      short loc_18000678E
0x180006780  mov     edx, [rbp+var_3C]
0x180006783  lea     rcx, [rbp+var_40]; this
0x180006787  inc     edx; unsigned int
0x180006789  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x18000678e  mov     r8, [rbx+20h]; unsigned __int8 *
0x180006792  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180006796  lea     rcx, [rbp+var_20]; this
0x18000679a  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18000679f  mov     byte ptr [rbx+38h], 1
0x1800067a3  jmp     loc_1800066B2
0x1800067a8  xor     al, al
0x1800067aa  mov     rbx, [rsp+70h+arg_8]
0x1800067b2  add     rsp, 70h
0x1800067b6  pop     r15
0x1800067b8  pop     r14
0x1800067ba  pop     r13
0x1800067bc  pop     r12
0x1800067be  pop     rdi
0x1800067bf  pop     rsi
0x1800067c0  pop     rbp
0x1800067c1  retn
```
