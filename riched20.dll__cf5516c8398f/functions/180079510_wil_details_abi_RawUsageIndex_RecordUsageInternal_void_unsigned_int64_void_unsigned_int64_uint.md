# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180079510`
- end: `0x1800796f4`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `484`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *, unsigned __int64, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18007941c`

## callees

- `0x180076670`
- `0x180076c58`
- `0x1800777b4`
- `0x180078c68`
- `0x180079510`
- `0x18007a164`
- `0x18007a9f0`
- `0x18007adac`

## import_xrefs

- `msvcrt!memmove_s` at `0x180079652`
- `msvcrt!memmove_s` at `0x180079652`

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
  char *v11; // rdi
  unsigned __int8 *v12; // r8
  char v13; // r14
  int v14; // eax
  unsigned __int8 *v15; // rax
  char v17; // cl
  unsigned __int64 Size; // rax
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // r9
  __int64 v21; // r8
  __int64 v22; // rsi
  __int16 v24; // [rsp+30h] [rbp-48h] BYREF
  char v25; // [rsp+32h] [rbp-46h]
  int v26; // [rsp+34h] [rbp-44h]
  __int16 v27; // [rsp+38h] [rbp-40h]
  __int128 v28; // [rsp+40h] [rbp-38h]
  __int16 v29; // [rsp+50h] [rbp-28h] BYREF
  char v30; // [rsp+52h] [rbp-26h]
  unsigned int v31; // [rsp+54h] [rbp-24h]
  __int16 v32; // [rsp+58h] [rbp-20h]
  __int64 v33; // [rsp+60h] [rbp-18h]
  void *v34; // [rsp+68h] [rbp-10h]
  void *Source; // [rsp+C0h] [rbp+48h] BYREF

  v6 = *((_QWORD *)this + 3);
  if ( v6 )
  {
    v11 = (char *)(v6 + 10);
    v12 = (unsigned __int8 *)*((_QWORD *)this + 4);
    v24 = *((_WORD *)this + 1);
    v25 = *((_BYTE *)this + 4);
    v27 = 0;
    v13 = 0;
    Source = v11;
    v26 = 0;
    v28 = 0;
    while ( 1 )
    {
      if ( !wil::details_abi::UsageIndexProperty::Read(
              (wil::details_abi::UsageIndexProperty *)&v24,
              (unsigned __int8 **)&Source,
              v12) )
      {
        v11 = (char *)Source;
        *((_QWORD *)this + 4) = Source;
        goto LABEL_8;
      }
      v14 = wil::details_abi::UsageIndexProperty::Compare((wil::details_abi::UsageIndexProperty *)&v24, a2, a3);
      if ( v14 < 0 )
      {
        Source = v11;
        goto LABEL_8;
      }
      if ( !v14 )
        break;
      v15 = wil::details_abi::RawUsageIndex::SkipValues(
              this,
              (struct wil::details_abi::UsageIndexProperty *)&v24,
              (unsigned __int8 *)Source);
      v12 = (unsigned __int8 *)*((_QWORD *)this + 4);
      v11 = (char *)v15;
      Source = v15;
    }
    Source = wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(
               this,
               (struct wil::details_abi::UsageIndexProperty *)&v24,
               (unsigned __int8 *)Source,
               a4,
               a5,
               a6);
    v11 = (char *)Source;
    if ( !Source )
      return 1;
    v13 = 1;
LABEL_8:
    if ( !v13 )
    {
      v26 = 1;
      v27 = a3;
      *(_QWORD *)&v28 = 0;
      *((_QWORD *)&v28 + 1) = a2;
      wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v24);
    }
    v29 = *((_WORD *)this + 3);
    v17 = *((_BYTE *)this + 8);
    v31 = a6;
    v30 = v17;
    v32 = a5;
    v33 = 0;
    v34 = a4;
    Size = wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v29);
    v19 = *((_QWORD *)this + 5);
    v20 = *((_QWORD *)this + 4);
    v22 = Size + v21;
    if ( ((v19 - v20) & -(__int64)(v20 < v19)) >= Size + v21 )
    {
      memmove_s(&v11[v22], v19 - v22 - (_QWORD)v11, v11, v20 - (_QWORD)v11);
      *((_QWORD *)this + 4) += v22;
      if ( v13 )
      {
        if ( v25 )
          wil::details_abi::UsageIndexProperty::UpdateCount((wil::details_abi::UsageIndexProperty *)&v24, v26 + 1);
      }
      else
      {
        wil::details_abi::UsageIndexProperty::Write(
          (wil::details_abi::UsageIndexProperty *)&v24,
          (unsigned __int8 **)&Source,
          *((unsigned __int8 **)this + 4));
      }
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v29,
        (unsigned __int8 **)&Source,
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
0x180079510  push    rbp
0x180079512  push    rbx
0x180079513  push    rsi
0x180079514  push    rdi
0x180079515  push    r12
0x180079517  push    r13
0x180079519  push    r14
0x18007951b  push    r15
0x18007951d  mov     rbp, rsp
0x180079520  sub     rsp, 78h
0x180079524  mov     rdi, [rcx+18h]
0x180079528  mov     r13, r9
0x18007952b  mov     r15, r8
0x18007952e  mov     r12, rdx
0x180079531  mov     rbx, rcx
0x180079534  test    rdi, rdi
0x180079537  jz      loc_1800796E1
0x18007953d  movzx   eax, word ptr [rcx+2]
0x180079541  add     rdi, 0Ah
0x180079545  mov     r8, [rcx+20h]
0x180079549  xorps   xmm0, xmm0
0x18007954c  mov     [rbp+var_48], ax
0x180079550  mov     al, [rcx+4]
0x180079553  mov     [rbp+var_46], al
0x180079556  xor     eax, eax
0x180079558  mov     [rbp+var_40], ax
0x18007955c  xor     r14b, r14b
0x18007955f  mov     [rbp+Source], rdi
0x180079563  mov     [rbp+var_44], 0
0x18007956a  movdqu  [rbp+var_38], xmm0
0x18007956f  jmp     short loc_1800795A9
0x180079571  mov     r8, r15; unsigned __int64
0x180079574  lea     rcx, [rbp+var_48]; this
0x180079578  mov     rdx, r12; void *
0x18007957b  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x180079580  test    eax, eax
0x180079582  js      loc_1800796A4
0x180079588  mov     r8, [rbp+Source]; unsigned __int8 *
0x18007958c  lea     rdx, [rbp+var_48]; struct wil::details_abi::UsageIndexProperty *
0x180079590  jz      loc_180079674
0x180079596  mov     rcx, rbx; this
0x180079599  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x18007959e  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800795a2  mov     rdi, rax
0x1800795a5  mov     [rbp+Source], rax
0x1800795a9  lea     rdx, [rbp+Source]; unsigned __int8 **
0x1800795ad  lea     rcx, [rbp+var_48]; this
0x1800795b1  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800795b6  mov     sil, al
0x1800795b9  test    al, al
0x1800795bb  jnz     short loc_180079571
0x1800795bd  mov     rdi, [rbp+Source]
0x1800795c1  mov     [rbx+20h], rdi
0x1800795c5  xor     r8d, r8d
0x1800795c8  test    r14b, r14b
0x1800795cb  jnz     short loc_1800795ED
0x1800795cd  lea     rcx, [rbp+var_48]; this
0x1800795d1  mov     [rbp+var_44], 1
0x1800795d8  mov     [rbp+var_40], r15w
0x1800795dd  mov     qword ptr [rbp+var_38], r8
0x1800795e1  mov     qword ptr [rbp+var_38+8], r12
0x1800795e5  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x1800795ea  mov     r8, rax
0x1800795ed  movzx   ecx, word ptr [rbx+6]
0x1800795f1  mov     eax, [rbp+arg_28]
0x1800795f4  mov     [rbp+var_28], cx
0x1800795f8  mov     cl, [rbx+8]
0x1800795fb  mov     [rbp+var_24], eax
0x1800795fe  mov     rax, [rbp+arg_20]
0x180079602  mov     [rbp+var_26], cl
0x180079605  lea     rcx, [rbp+var_28]; this
0x180079609  mov     [rbp+var_20], ax
0x18007960d  mov     [rbp+var_18], 0
0x180079615  mov     [rbp+var_10], r13
0x180079619  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18007961e  mov     rdx, [rbx+28h]
0x180079622  mov     r9, [rbx+20h]
0x180079626  mov     rcx, rdx
0x180079629  sub     rcx, r9
0x18007962c  lea     rsi, [rax+r8]
0x180079630  cmp     r9, rdx
0x180079633  sbb     rax, rax
0x180079636  and     rax, rcx
0x180079639  cmp     rax, rsi
0x18007963c  jb      loc_1800796E1
0x180079642  sub     rdx, rsi
0x180079645  lea     rcx, [rsi+rdi]; Destination
0x180079649  sub     rdx, rdi; DestinationSize
0x18007964c  sub     r9, rdi; SourceSize
0x18007964f  mov     r8, rdi; Source
0x180079652  call    cs:__imp_memmove_s
0x180079658  add     [rbx+20h], rsi
0x18007965c  test    r14b, r14b
0x18007965f  jnz     short loc_1800796B6
0x180079661  mov     r8, [rbx+20h]; unsigned __int8 *
0x180079665  lea     rdx, [rbp+Source]; unsigned __int8 **
0x180079669  lea     rcx, [rbp+var_48]; this
0x18007966d  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180079672  jmp     short loc_1800796CA
0x180079674  mov     ecx, [rbp+arg_28]
0x180079677  mov     r9, r13; void *
0x18007967a  mov     [rsp+78h+var_50], ecx; unsigned int
0x18007967e  mov     rcx, [rbp+arg_20]
0x180079682  mov     [rsp+78h+var_58], rcx; unsigned __int64
0x180079687  mov     rcx, rbx; this
0x18007968a  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18007968f  mov     [rbp+Source], rax
0x180079693  mov     rdi, rax
0x180079696  test    rax, rax
0x180079699  jnz     short loc_18007969F
0x18007969b  mov     al, 1
0x18007969d  jmp     short loc_1800796E3
0x18007969f  mov     r14b, 1
0x1800796a2  jmp     short loc_1800796A8
0x1800796a4  mov     [rbp+Source], rdi
0x1800796a8  test    sil, sil
0x1800796ab  jnz     loc_1800795C5
0x1800796b1  jmp     loc_1800795C1
0x1800796b6  cmp     [rbp+var_46], 0
0x1800796ba  jz      short loc_1800796CA
0x1800796bc  mov     edx, [rbp+var_44]
0x1800796bf  lea     rcx, [rbp+var_48]; this
0x1800796c3  inc     edx; unsigned int
0x1800796c5  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x1800796ca  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800796ce  lea     rdx, [rbp+Source]; unsigned __int8 **
0x1800796d2  lea     rcx, [rbp+var_28]; this
0x1800796d6  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1800796db  mov     byte ptr [rbx+38h], 1
0x1800796df  jmp     short loc_18007969B
0x1800796e1  xor     al, al
0x1800796e3  add     rsp, 78h
0x1800796e7  pop     r15
0x1800796e9  pop     r14
0x1800796eb  pop     r13
0x1800796ed  pop     r12
0x1800796ef  pop     rdi
0x1800796f0  pop     rsi
0x1800796f1  pop     rbx
0x1800796f2  pop     rbp
0x1800796f3  retn
```
