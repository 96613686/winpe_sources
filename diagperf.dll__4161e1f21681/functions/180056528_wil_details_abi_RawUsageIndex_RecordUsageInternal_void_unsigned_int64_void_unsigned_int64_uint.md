# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180056528`
- end: `0x180056702`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `474`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180056434`

## callees

- `0x180056528`
- `0x18007c778`
- `0x18007dfe8`
- `0x18007f0b4`
- `0x1800808e0`
- `0x180081c6c`
- `0x180082324`
- `0x1800826d4`

## import_xrefs

- `msvcrt!memmove_s` at `0x180056698`
- `msvcrt!memmove_s` at `0x180056698`

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
0x180056528  mov     [rsp-38h+arg_8], rbx
0x18005652d  mov     [rsp-38h+arg_18], r9
0x180056532  push    rbp
0x180056533  push    rsi
0x180056534  push    rdi
0x180056535  push    r12
0x180056537  push    r13
0x180056539  push    r14
0x18005653b  push    r15
0x18005653d  mov     rbp, rsp
0x180056540  sub     rsp, 70h
0x180056544  mov     rdi, [rcx+18h]
0x180056548  mov     r14, r8
0x18005654b  mov     r15, rdx
0x18005654e  mov     rbx, rcx
0x180056551  test    rdi, rdi
0x180056554  jz      loc_1800566E8
0x18005655a  movzx   eax, word ptr [rcx+2]
0x18005655e  add     rdi, 0Ah
0x180056562  mov     [rbp+var_40], ax
0x180056566  xorps   xmm0, xmm0
0x180056569  mov     al, [rcx+4]
0x18005656c  mov     [rbp+var_3E], al
0x18005656f  xor     eax, eax
0x180056571  mov     [rbp+var_38], ax
0x180056575  xor     sil, sil
0x180056578  mov     [rbp+arg_0], rdi
0x18005657c  mov     [rbp+var_3C], 0
0x180056583  movdqu  [rbp+var_30], xmm0
0x180056588  mov     r8, [rbx+20h]; unsigned __int8 *
0x18005658c  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180056590  lea     rcx, [rbp+var_40]; this
0x180056594  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180056599  mov     r12d, [rbp+arg_28]
0x18005659d  mov     r13, [rbp+arg_20]
0x1800565a1  test    al, al
0x1800565a3  jz      short loc_18005660C
0x1800565a5  mov     r8, r14; unsigned __int64
0x1800565a8  lea     rcx, [rbp+var_40]; this
0x1800565ac  mov     rdx, r15; void *
0x1800565af  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x1800565b4  test    eax, eax
0x1800565b6  js      short loc_1800565FE
0x1800565b8  mov     r8, [rbp+arg_0]; unsigned __int8 *
0x1800565bc  lea     rdx, [rbp+var_40]; struct wil::details_abi::UsageIndexProperty *
0x1800565c0  mov     rcx, rbx; this
0x1800565c3  jz      short loc_1800565D3
0x1800565c5  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x1800565ca  mov     rdi, rax
0x1800565cd  mov     [rbp+arg_0], rax
0x1800565d1  jmp     short loc_180056588
0x1800565d3  mov     r9, [rbp+arg_18]; void *
0x1800565d7  mov     [rsp+70h+var_48], r12d; unsigned int
0x1800565dc  mov     [rsp+70h+var_50], r13; unsigned __int64
0x1800565e1  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x1800565e6  mov     [rbp+arg_0], rax
0x1800565ea  mov     rdi, rax
0x1800565ed  test    rax, rax
0x1800565f0  jnz     short loc_1800565F9
0x1800565f2  mov     al, 1
0x1800565f4  jmp     loc_1800566EA
0x1800565f9  mov     sil, 1
0x1800565fc  jmp     short loc_180056602
0x1800565fe  mov     [rbp+arg_0], rdi
0x180056602  xor     r8d, r8d
0x180056605  test    sil, sil
0x180056608  jnz     short loc_180056638
0x18005660a  jmp     short loc_180056614
0x18005660c  mov     rdi, [rbp+arg_0]
0x180056610  mov     [rbx+20h], rdi
0x180056614  lea     rcx, [rbp+var_40]; this
0x180056618  mov     [rbp+var_3C], 1
0x18005661f  mov     [rbp+var_38], r14w
0x180056624  mov     qword ptr [rbp+var_30], 0
0x18005662c  mov     qword ptr [rbp+var_30+8], r15
0x180056630  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180056635  mov     r8, rax
0x180056638  movzx   ecx, word ptr [rbx+6]
0x18005663c  mov     rax, [rbp+arg_18]
0x180056640  mov     [rbp+var_20], cx
0x180056644  mov     cl, [rbx+8]
0x180056647  mov     [rbp+var_1E], cl
0x18005664a  lea     rcx, [rbp+var_20]; this
0x18005664e  mov     [rbp+var_1C], r12d
0x180056652  mov     [rbp+var_18], r13w
0x180056657  mov     [rbp+var_10], 0
0x18005665f  mov     [rbp+var_8], rax
0x180056663  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180056668  mov     rdx, [rbx+28h]
0x18005666c  mov     r9, [rbx+20h]
0x180056670  mov     rcx, rdx
0x180056673  sub     rcx, r9
0x180056676  lea     r14, [rax+r8]
0x18005667a  cmp     r9, rdx
0x18005667d  sbb     rax, rax
0x180056680  and     rax, rcx
0x180056683  cmp     rax, r14
0x180056686  jb      short loc_1800566E8
0x180056688  sub     rdx, r14
0x18005668b  lea     rcx, [r14+rdi]; Destination
0x18005668f  sub     rdx, rdi; DestinationSize
0x180056692  sub     r9, rdi; SourceSize
0x180056695  mov     r8, rdi; Source
0x180056698  call    cs:__imp_memmove_s
0x18005669e  add     [rbx+20h], r14
0x1800566a2  test    sil, sil
0x1800566a5  jnz     short loc_1800566BA
0x1800566a7  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800566ab  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x1800566af  lea     rcx, [rbp+var_40]; this
0x1800566b3  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1800566b8  jmp     short loc_1800566CE
0x1800566ba  cmp     [rbp+var_3E], 0
0x1800566be  jz      short loc_1800566CE
0x1800566c0  mov     edx, [rbp+var_3C]
0x1800566c3  lea     rcx, [rbp+var_40]; this
0x1800566c7  inc     edx; unsigned int
0x1800566c9  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x1800566ce  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800566d2  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x1800566d6  lea     rcx, [rbp+var_20]; this
0x1800566da  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1800566df  mov     byte ptr [rbx+38h], 1
0x1800566e3  jmp     loc_1800565F2
0x1800566e8  xor     al, al
0x1800566ea  mov     rbx, [rsp+70h+arg_8]
0x1800566f2  add     rsp, 70h
0x1800566f6  pop     r15
0x1800566f8  pop     r14
0x1800566fa  pop     r13
0x1800566fc  pop     r12
0x1800566fe  pop     rdi
0x1800566ff  pop     rsi
0x180056700  pop     rbp
0x180056701  retn
```
