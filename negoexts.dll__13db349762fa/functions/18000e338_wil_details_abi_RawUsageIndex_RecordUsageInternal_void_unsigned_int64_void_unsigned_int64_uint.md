# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18000e338`
- end: `0x18000e512`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `474`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000e244`

## callees

- `0x18000e338`
- `0x180010e68`
- `0x180011258`
- `0x180011e84`
- `0x1800130c0`
- `0x180014090`
- `0x180014bc4`
- `0x180014fbc`

## import_xrefs

- `msvcrt!memmove_s` at `0x18000e4a8`
- `msvcrt!memmove_s` at `0x18000e4a8`

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
0x18000e338  mov     [rsp-38h+arg_8], rbx
0x18000e33d  mov     [rsp-38h+arg_18], r9
0x18000e342  push    rbp
0x18000e343  push    rsi
0x18000e344  push    rdi
0x18000e345  push    r12
0x18000e347  push    r13
0x18000e349  push    r14
0x18000e34b  push    r15
0x18000e34d  mov     rbp, rsp
0x18000e350  sub     rsp, 70h
0x18000e354  mov     rdi, [rcx+18h]
0x18000e358  mov     r14, r8
0x18000e35b  mov     r15, rdx
0x18000e35e  mov     rbx, rcx
0x18000e361  test    rdi, rdi
0x18000e364  jz      loc_18000E4F8
0x18000e36a  movzx   eax, word ptr [rcx+2]
0x18000e36e  add     rdi, 0Ah
0x18000e372  mov     [rbp+var_40], ax
0x18000e376  xorps   xmm0, xmm0
0x18000e379  mov     al, [rcx+4]
0x18000e37c  mov     [rbp+var_3E], al
0x18000e37f  xor     eax, eax
0x18000e381  mov     [rbp+var_38], ax
0x18000e385  xor     sil, sil
0x18000e388  mov     [rbp+arg_0], rdi
0x18000e38c  mov     [rbp+var_3C], 0
0x18000e393  movdqu  [rbp+var_30], xmm0
0x18000e398  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000e39c  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x18000e3a0  lea     rcx, [rbp+var_40]; this
0x18000e3a4  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000e3a9  mov     r12d, [rbp+arg_28]
0x18000e3ad  mov     r13, [rbp+arg_20]
0x18000e3b1  test    al, al
0x18000e3b3  jz      short loc_18000E41C
0x18000e3b5  mov     r8, r14; unsigned __int64
0x18000e3b8  lea     rcx, [rbp+var_40]; this
0x18000e3bc  mov     rdx, r15; void *
0x18000e3bf  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x18000e3c4  test    eax, eax
0x18000e3c6  js      short loc_18000E40E
0x18000e3c8  mov     r8, [rbp+arg_0]; unsigned __int8 *
0x18000e3cc  lea     rdx, [rbp+var_40]; struct wil::details_abi::UsageIndexProperty *
0x18000e3d0  mov     rcx, rbx; this
0x18000e3d3  jz      short loc_18000E3E3
0x18000e3d5  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x18000e3da  mov     rdi, rax
0x18000e3dd  mov     [rbp+arg_0], rax
0x18000e3e1  jmp     short loc_18000E398
0x18000e3e3  mov     r9, [rbp+arg_18]; void *
0x18000e3e7  mov     [rsp+70h+var_48], r12d; unsigned int
0x18000e3ec  mov     [rsp+70h+var_50], r13; unsigned __int64
0x18000e3f1  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18000e3f6  mov     [rbp+arg_0], rax
0x18000e3fa  mov     rdi, rax
0x18000e3fd  test    rax, rax
0x18000e400  jnz     short loc_18000E409
0x18000e402  mov     al, 1
0x18000e404  jmp     loc_18000E4FA
0x18000e409  mov     sil, 1
0x18000e40c  jmp     short loc_18000E412
0x18000e40e  mov     [rbp+arg_0], rdi
0x18000e412  xor     r8d, r8d
0x18000e415  test    sil, sil
0x18000e418  jnz     short loc_18000E448
0x18000e41a  jmp     short loc_18000E424
0x18000e41c  mov     rdi, [rbp+arg_0]
0x18000e420  mov     [rbx+20h], rdi
0x18000e424  lea     rcx, [rbp+var_40]; this
0x18000e428  mov     [rbp+var_3C], 1
0x18000e42f  mov     [rbp+var_38], r14w
0x18000e434  mov     qword ptr [rbp+var_30], 0
0x18000e43c  mov     qword ptr [rbp+var_30+8], r15
0x18000e440  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18000e445  mov     r8, rax
0x18000e448  movzx   ecx, word ptr [rbx+6]
0x18000e44c  mov     rax, [rbp+arg_18]
0x18000e450  mov     [rbp+var_20], cx
0x18000e454  mov     cl, [rbx+8]
0x18000e457  mov     [rbp+var_1E], cl
0x18000e45a  lea     rcx, [rbp+var_20]; this
0x18000e45e  mov     [rbp+var_1C], r12d
0x18000e462  mov     [rbp+var_18], r13w
0x18000e467  mov     [rbp+var_10], 0
0x18000e46f  mov     [rbp+var_8], rax
0x18000e473  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18000e478  mov     rdx, [rbx+28h]
0x18000e47c  mov     r9, [rbx+20h]
0x18000e480  mov     rcx, rdx
0x18000e483  sub     rcx, r9
0x18000e486  lea     r14, [rax+r8]
0x18000e48a  cmp     r9, rdx
0x18000e48d  sbb     rax, rax
0x18000e490  and     rax, rcx
0x18000e493  cmp     rax, r14
0x18000e496  jb      short loc_18000E4F8
0x18000e498  sub     rdx, r14
0x18000e49b  lea     rcx, [r14+rdi]; Destination
0x18000e49f  sub     rdx, rdi; DestinationSize
0x18000e4a2  sub     r9, rdi; SourceSize
0x18000e4a5  mov     r8, rdi; Source
0x18000e4a8  call    cs:__imp_memmove_s
0x18000e4ae  add     [rbx+20h], r14
0x18000e4b2  test    sil, sil
0x18000e4b5  jnz     short loc_18000E4CA
0x18000e4b7  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000e4bb  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x18000e4bf  lea     rcx, [rbp+var_40]; this
0x18000e4c3  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18000e4c8  jmp     short loc_18000E4DE
0x18000e4ca  cmp     [rbp+var_3E], 0
0x18000e4ce  jz      short loc_18000E4DE
0x18000e4d0  mov     edx, [rbp+var_3C]
0x18000e4d3  lea     rcx, [rbp+var_40]; this
0x18000e4d7  inc     edx; unsigned int
0x18000e4d9  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x18000e4de  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000e4e2  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x18000e4e6  lea     rcx, [rbp+var_20]; this
0x18000e4ea  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18000e4ef  mov     byte ptr [rbx+38h], 1
0x18000e4f3  jmp     loc_18000E402
0x18000e4f8  xor     al, al
0x18000e4fa  mov     rbx, [rsp+70h+arg_8]
0x18000e502  add     rsp, 70h
0x18000e506  pop     r15
0x18000e508  pop     r14
0x18000e50a  pop     r13
0x18000e50c  pop     r12
0x18000e50e  pop     rdi
0x18000e50f  pop     rsi
0x18000e510  pop     rbp
0x18000e511  retn
```
