# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x18001c518`
- end: `0x18001c6f2`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `474`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001c424`

## callees

- `0x180019638`
- `0x1800198c0`
- `0x180019c3c`
- `0x18001bf9c`
- `0x18001c518`
- `0x18001cc34`
- `0x18001d070`
- `0x18001d370`

## import_xrefs

- `msvcrt!memmove_s` at `0x18001c688`
- `msvcrt!memmove_s` at `0x18001c688`

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
0x18001c518  mov     [rsp-38h+arg_8], rbx
0x18001c51d  mov     [rsp-38h+arg_18], r9
0x18001c522  push    rbp
0x18001c523  push    rsi
0x18001c524  push    rdi
0x18001c525  push    r12
0x18001c527  push    r13
0x18001c529  push    r14
0x18001c52b  push    r15
0x18001c52d  mov     rbp, rsp
0x18001c530  sub     rsp, 70h
0x18001c534  mov     rdi, [rcx+18h]
0x18001c538  mov     r14, r8
0x18001c53b  mov     r15, rdx
0x18001c53e  mov     rbx, rcx
0x18001c541  test    rdi, rdi
0x18001c544  jz      loc_18001C6D8
0x18001c54a  movzx   eax, word ptr [rcx+2]
0x18001c54e  add     rdi, 0Ah
0x18001c552  mov     [rbp+var_40], ax
0x18001c556  xorps   xmm0, xmm0
0x18001c559  mov     al, [rcx+4]
0x18001c55c  mov     [rbp+var_3E], al
0x18001c55f  xor     eax, eax
0x18001c561  mov     [rbp+var_38], ax
0x18001c565  xor     sil, sil
0x18001c568  mov     [rbp+arg_0], rdi
0x18001c56c  mov     [rbp+var_3C], 0
0x18001c573  movdqu  [rbp+var_30], xmm0
0x18001c578  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001c57c  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x18001c580  lea     rcx, [rbp+var_40]; this
0x18001c584  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18001c589  mov     r12d, [rbp+arg_28]
0x18001c58d  mov     r13, [rbp+arg_20]
0x18001c591  test    al, al
0x18001c593  jz      short loc_18001C5FC
0x18001c595  mov     r8, r14; unsigned __int64
0x18001c598  lea     rcx, [rbp+var_40]; this
0x18001c59c  mov     rdx, r15; void *
0x18001c59f  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x18001c5a4  test    eax, eax
0x18001c5a6  js      short loc_18001C5EE
0x18001c5a8  mov     r8, [rbp+arg_0]; unsigned __int8 *
0x18001c5ac  lea     rdx, [rbp+var_40]; struct wil::details_abi::UsageIndexProperty *
0x18001c5b0  mov     rcx, rbx; this
0x18001c5b3  jz      short loc_18001C5C3
0x18001c5b5  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x18001c5ba  mov     rdi, rax
0x18001c5bd  mov     [rbp+arg_0], rax
0x18001c5c1  jmp     short loc_18001C578
0x18001c5c3  mov     r9, [rbp+arg_18]; void *
0x18001c5c7  mov     [rsp+70h+var_48], r12d; unsigned int
0x18001c5cc  mov     [rsp+70h+var_50], r13; unsigned __int64
0x18001c5d1  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18001c5d6  mov     [rbp+arg_0], rax
0x18001c5da  mov     rdi, rax
0x18001c5dd  test    rax, rax
0x18001c5e0  jnz     short loc_18001C5E9
0x18001c5e2  mov     al, 1
0x18001c5e4  jmp     loc_18001C6DA
0x18001c5e9  mov     sil, 1
0x18001c5ec  jmp     short loc_18001C5F2
0x18001c5ee  mov     [rbp+arg_0], rdi
0x18001c5f2  xor     r8d, r8d
0x18001c5f5  test    sil, sil
0x18001c5f8  jnz     short loc_18001C628
0x18001c5fa  jmp     short loc_18001C604
0x18001c5fc  mov     rdi, [rbp+arg_0]
0x18001c600  mov     [rbx+20h], rdi
0x18001c604  lea     rcx, [rbp+var_40]; this
0x18001c608  mov     [rbp+var_3C], 1
0x18001c60f  mov     [rbp+var_38], r14w
0x18001c614  mov     qword ptr [rbp+var_30], 0
0x18001c61c  mov     qword ptr [rbp+var_30+8], r15
0x18001c620  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18001c625  mov     r8, rax
0x18001c628  movzx   ecx, word ptr [rbx+6]
0x18001c62c  mov     rax, [rbp+arg_18]
0x18001c630  mov     [rbp+var_20], cx
0x18001c634  mov     cl, [rbx+8]
0x18001c637  mov     [rbp+var_1E], cl
0x18001c63a  lea     rcx, [rbp+var_20]; this
0x18001c63e  mov     [rbp+var_1C], r12d
0x18001c642  mov     [rbp+var_18], r13w
0x18001c647  mov     [rbp+var_10], 0
0x18001c64f  mov     [rbp+var_8], rax
0x18001c653  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18001c658  mov     rdx, [rbx+28h]
0x18001c65c  mov     r9, [rbx+20h]
0x18001c660  mov     rcx, rdx
0x18001c663  sub     rcx, r9
0x18001c666  lea     r14, [rax+r8]
0x18001c66a  cmp     r9, rdx
0x18001c66d  sbb     rax, rax
0x18001c670  and     rax, rcx
0x18001c673  cmp     rax, r14
0x18001c676  jb      short loc_18001C6D8
0x18001c678  sub     rdx, r14
0x18001c67b  lea     rcx, [r14+rdi]; Destination
0x18001c67f  sub     rdx, rdi; DestinationSize
0x18001c682  sub     r9, rdi; SourceSize
0x18001c685  mov     r8, rdi; Source
0x18001c688  call    cs:__imp_memmove_s
0x18001c68e  add     [rbx+20h], r14
0x18001c692  test    sil, sil
0x18001c695  jnz     short loc_18001C6AA
0x18001c697  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001c69b  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x18001c69f  lea     rcx, [rbp+var_40]; this
0x18001c6a3  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18001c6a8  jmp     short loc_18001C6BE
0x18001c6aa  cmp     [rbp+var_3E], 0
0x18001c6ae  jz      short loc_18001C6BE
0x18001c6b0  mov     edx, [rbp+var_3C]
0x18001c6b3  lea     rcx, [rbp+var_40]; this
0x18001c6b7  inc     edx; unsigned int
0x18001c6b9  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x18001c6be  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001c6c2  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x18001c6c6  lea     rcx, [rbp+var_20]; this
0x18001c6ca  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18001c6cf  mov     byte ptr [rbx+38h], 1
0x18001c6d3  jmp     loc_18001C5E2
0x18001c6d8  xor     al, al
0x18001c6da  mov     rbx, [rsp+70h+arg_8]
0x18001c6e2  add     rsp, 70h
0x18001c6e6  pop     r15
0x18001c6e8  pop     r14
0x18001c6ea  pop     r13
0x18001c6ec  pop     r12
0x18001c6ee  pop     rdi
0x18001c6ef  pop     rsi
0x18001c6f0  pop     rbp
0x18001c6f1  retn
```
