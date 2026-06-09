# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x140009108`
- end: `0x1400092e2`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `474`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140009014`

## callees

- `0x140005d28`
- `0x14000613c`
- `0x140006ba8`
- `0x140008ac8`
- `0x140009108`
- `0x140009d74`
- `0x14000a9e0`
- `0x14000aef4`

## import_xrefs

- `msvcrt!memmove_s` at `0x140009278`
- `msvcrt!memmove_s` at `0x140009278`

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
0x140009108  mov     [rsp-38h+arg_8], rbx
0x14000910d  mov     [rsp-38h+arg_18], r9
0x140009112  push    rbp
0x140009113  push    rsi
0x140009114  push    rdi
0x140009115  push    r12
0x140009117  push    r13
0x140009119  push    r14
0x14000911b  push    r15
0x14000911d  mov     rbp, rsp
0x140009120  sub     rsp, 70h
0x140009124  mov     rdi, [rcx+18h]
0x140009128  mov     r14, r8
0x14000912b  mov     r15, rdx
0x14000912e  mov     rbx, rcx
0x140009131  test    rdi, rdi
0x140009134  jz      loc_1400092C8
0x14000913a  movzx   eax, word ptr [rcx+2]
0x14000913e  add     rdi, 0Ah
0x140009142  mov     [rbp+var_40], ax
0x140009146  xorps   xmm0, xmm0
0x140009149  mov     al, [rcx+4]
0x14000914c  mov     [rbp+var_3E], al
0x14000914f  xor     eax, eax
0x140009151  mov     [rbp+var_38], ax
0x140009155  xor     sil, sil
0x140009158  mov     [rbp+arg_0], rdi
0x14000915c  mov     [rbp+var_3C], 0
0x140009163  movdqu  [rbp+var_30], xmm0
0x140009168  mov     r8, [rbx+20h]; unsigned __int8 *
0x14000916c  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x140009170  lea     rcx, [rbp+var_40]; this
0x140009174  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140009179  mov     r12d, [rbp+arg_28]
0x14000917d  mov     r13, [rbp+arg_20]
0x140009181  test    al, al
0x140009183  jz      short loc_1400091EC
0x140009185  mov     r8, r14; unsigned __int64
0x140009188  lea     rcx, [rbp+var_40]; this
0x14000918c  mov     rdx, r15; void *
0x14000918f  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x140009194  test    eax, eax
0x140009196  js      short loc_1400091DE
0x140009198  mov     r8, [rbp+arg_0]; unsigned __int8 *
0x14000919c  lea     rdx, [rbp+var_40]; struct wil::details_abi::UsageIndexProperty *
0x1400091a0  mov     rcx, rbx; this
0x1400091a3  jz      short loc_1400091B3
0x1400091a5  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x1400091aa  mov     rdi, rax
0x1400091ad  mov     [rbp+arg_0], rax
0x1400091b1  jmp     short loc_140009168
0x1400091b3  mov     r9, [rbp+arg_18]; void *
0x1400091b7  mov     [rsp+70h+var_48], r12d; unsigned int
0x1400091bc  mov     [rsp+70h+var_50], r13; unsigned __int64
0x1400091c1  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x1400091c6  mov     [rbp+arg_0], rax
0x1400091ca  mov     rdi, rax
0x1400091cd  test    rax, rax
0x1400091d0  jnz     short loc_1400091D9
0x1400091d2  mov     al, 1
0x1400091d4  jmp     loc_1400092CA
0x1400091d9  mov     sil, 1
0x1400091dc  jmp     short loc_1400091E2
0x1400091de  mov     [rbp+arg_0], rdi
0x1400091e2  xor     r8d, r8d
0x1400091e5  test    sil, sil
0x1400091e8  jnz     short loc_140009218
0x1400091ea  jmp     short loc_1400091F4
0x1400091ec  mov     rdi, [rbp+arg_0]
0x1400091f0  mov     [rbx+20h], rdi
0x1400091f4  lea     rcx, [rbp+var_40]; this
0x1400091f8  mov     [rbp+var_3C], 1
0x1400091ff  mov     [rbp+var_38], r14w
0x140009204  mov     qword ptr [rbp+var_30], 0
0x14000920c  mov     qword ptr [rbp+var_30+8], r15
0x140009210  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x140009215  mov     r8, rax
0x140009218  movzx   ecx, word ptr [rbx+6]
0x14000921c  mov     rax, [rbp+arg_18]
0x140009220  mov     [rbp+var_20], cx
0x140009224  mov     cl, [rbx+8]
0x140009227  mov     [rbp+var_1E], cl
0x14000922a  lea     rcx, [rbp+var_20]; this
0x14000922e  mov     [rbp+var_1C], r12d
0x140009232  mov     [rbp+var_18], r13w
0x140009237  mov     [rbp+var_10], 0
0x14000923f  mov     [rbp+var_8], rax
0x140009243  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x140009248  mov     rdx, [rbx+28h]
0x14000924c  mov     r9, [rbx+20h]
0x140009250  mov     rcx, rdx
0x140009253  sub     rcx, r9
0x140009256  lea     r14, [rax+r8]
0x14000925a  cmp     r9, rdx
0x14000925d  sbb     rax, rax
0x140009260  and     rax, rcx
0x140009263  cmp     rax, r14
0x140009266  jb      short loc_1400092C8
0x140009268  sub     rdx, r14
0x14000926b  lea     rcx, [r14+rdi]; Destination
0x14000926f  sub     rdx, rdi; DestinationSize
0x140009272  sub     r9, rdi; SourceSize
0x140009275  mov     r8, rdi; Source
0x140009278  call    cs:__imp_memmove_s
0x14000927e  add     [rbx+20h], r14
0x140009282  test    sil, sil
0x140009285  jnz     short loc_14000929A
0x140009287  mov     r8, [rbx+20h]; unsigned __int8 *
0x14000928b  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x14000928f  lea     rcx, [rbp+var_40]; this
0x140009293  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x140009298  jmp     short loc_1400092AE
0x14000929a  cmp     [rbp+var_3E], 0
0x14000929e  jz      short loc_1400092AE
0x1400092a0  mov     edx, [rbp+var_3C]
0x1400092a3  lea     rcx, [rbp+var_40]; this
0x1400092a7  inc     edx; unsigned int
0x1400092a9  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x1400092ae  mov     r8, [rbx+20h]; unsigned __int8 *
0x1400092b2  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x1400092b6  lea     rcx, [rbp+var_20]; this
0x1400092ba  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1400092bf  mov     byte ptr [rbx+38h], 1
0x1400092c3  jmp     loc_1400091D2
0x1400092c8  xor     al, al
0x1400092ca  mov     rbx, [rsp+70h+arg_8]
0x1400092d2  add     rsp, 70h
0x1400092d6  pop     r15
0x1400092d8  pop     r14
0x1400092da  pop     r13
0x1400092dc  pop     r12
0x1400092de  pop     rdi
0x1400092df  pop     rsi
0x1400092e0  pop     rbp
0x1400092e1  retn
```
