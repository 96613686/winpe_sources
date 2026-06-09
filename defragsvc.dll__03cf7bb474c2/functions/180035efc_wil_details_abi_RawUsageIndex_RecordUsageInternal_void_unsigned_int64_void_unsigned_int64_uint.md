# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180035efc`
- end: `0x1800360d6`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `474`
- prototype: `bool __usercall@<al>(wil::details_abi::RawUsageIndex *__hidden this@<rcx>, void *@<rdx>, unsigned __int64@<r8>, void *@<r9>, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180035e08`

## callees

- `0x180035efc`
- `0x18004f90c`
- `0x18004fb84`
- `0x180050348`
- `0x18005113c`
- `0x180051cf4`
- `0x1800522d8`
- `0x1800525fc`

## import_xrefs

- `msvcrt!memmove_s` at `0x18003606c`
- `msvcrt!memmove_s` at `0x18003606c`

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
0x180035efc  mov     [rsp-38h+arg_8], rbx
0x180035f01  mov     [rsp-38h+arg_18], r9
0x180035f06  push    rbp
0x180035f07  push    rsi
0x180035f08  push    rdi
0x180035f09  push    r12
0x180035f0b  push    r13
0x180035f0d  push    r14
0x180035f0f  push    r15
0x180035f11  mov     rbp, rsp
0x180035f14  sub     rsp, 70h
0x180035f18  mov     rdi, [rcx+18h]
0x180035f1c  mov     r14, r8
0x180035f1f  mov     r15, rdx
0x180035f22  mov     rbx, rcx
0x180035f25  test    rdi, rdi
0x180035f28  jz      loc_1800360BC
0x180035f2e  movzx   eax, word ptr [rcx+2]
0x180035f32  add     rdi, 0Ah
0x180035f36  mov     [rbp+var_40], ax
0x180035f3a  xorps   xmm0, xmm0
0x180035f3d  mov     al, [rcx+4]
0x180035f40  mov     [rbp+var_3E], al
0x180035f43  xor     eax, eax
0x180035f45  mov     [rbp+var_38], ax
0x180035f49  xor     sil, sil
0x180035f4c  mov     [rbp+arg_0], rdi
0x180035f50  mov     [rbp+var_3C], 0
0x180035f57  movdqu  [rbp+var_30], xmm0
0x180035f5c  mov     r8, [rbx+20h]; unsigned __int8 *
0x180035f60  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180035f64  lea     rcx, [rbp+var_40]; this
0x180035f68  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180035f6d  mov     r12d, [rbp+arg_28]
0x180035f71  mov     r13, [rbp+arg_20]
0x180035f75  test    al, al
0x180035f77  jz      short loc_180035FE0
0x180035f79  mov     r8, r14; unsigned __int64
0x180035f7c  lea     rcx, [rbp+var_40]; this
0x180035f80  mov     rdx, r15; void *
0x180035f83  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x180035f88  test    eax, eax
0x180035f8a  js      short loc_180035FD2
0x180035f8c  mov     r8, [rbp+arg_0]; unsigned __int8 *
0x180035f90  lea     rdx, [rbp+var_40]; struct wil::details_abi::UsageIndexProperty *
0x180035f94  mov     rcx, rbx; this
0x180035f97  jz      short loc_180035FA7
0x180035f99  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x180035f9e  mov     rdi, rax
0x180035fa1  mov     [rbp+arg_0], rax
0x180035fa5  jmp     short loc_180035F5C
0x180035fa7  mov     r9, [rbp+arg_18]; void *
0x180035fab  mov     [rsp+70h+var_48], r12d; unsigned int
0x180035fb0  mov     [rsp+70h+var_50], r13; unsigned __int64
0x180035fb5  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x180035fba  mov     [rbp+arg_0], rax
0x180035fbe  mov     rdi, rax
0x180035fc1  test    rax, rax
0x180035fc4  jnz     short loc_180035FCD
0x180035fc6  mov     al, 1
0x180035fc8  jmp     loc_1800360BE
0x180035fcd  mov     sil, 1
0x180035fd0  jmp     short loc_180035FD6
0x180035fd2  mov     [rbp+arg_0], rdi
0x180035fd6  xor     r8d, r8d
0x180035fd9  test    sil, sil
0x180035fdc  jnz     short loc_18003600C
0x180035fde  jmp     short loc_180035FE8
0x180035fe0  mov     rdi, [rbp+arg_0]
0x180035fe4  mov     [rbx+20h], rdi
0x180035fe8  lea     rcx, [rbp+var_40]; this
0x180035fec  mov     [rbp+var_3C], 1
0x180035ff3  mov     [rbp+var_38], r14w
0x180035ff8  mov     qword ptr [rbp+var_30], 0
0x180036000  mov     qword ptr [rbp+var_30+8], r15
0x180036004  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180036009  mov     r8, rax
0x18003600c  movzx   ecx, word ptr [rbx+6]
0x180036010  mov     rax, [rbp+arg_18]
0x180036014  mov     [rbp+var_20], cx
0x180036018  mov     cl, [rbx+8]
0x18003601b  mov     [rbp+var_1E], cl
0x18003601e  lea     rcx, [rbp+var_20]; this
0x180036022  mov     [rbp+var_1C], r12d
0x180036026  mov     [rbp+var_18], r13w
0x18003602b  mov     [rbp+var_10], 0
0x180036033  mov     [rbp+var_8], rax
0x180036037  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18003603c  mov     rdx, [rbx+28h]
0x180036040  mov     r9, [rbx+20h]
0x180036044  mov     rcx, rdx
0x180036047  sub     rcx, r9
0x18003604a  lea     r14, [rax+r8]
0x18003604e  cmp     r9, rdx
0x180036051  sbb     rax, rax
0x180036054  and     rax, rcx
0x180036057  cmp     rax, r14
0x18003605a  jb      short loc_1800360BC
0x18003605c  sub     rdx, r14
0x18003605f  lea     rcx, [r14+rdi]; Destination
0x180036063  sub     rdx, rdi; DestinationSize
0x180036066  sub     r9, rdi; SourceSize
0x180036069  mov     r8, rdi; Source
0x18003606c  call    cs:__imp_memmove_s
0x180036072  add     [rbx+20h], r14
0x180036076  test    sil, sil
0x180036079  jnz     short loc_18003608E
0x18003607b  mov     r8, [rbx+20h]; unsigned __int8 *
0x18003607f  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x180036083  lea     rcx, [rbp+var_40]; this
0x180036087  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18003608c  jmp     short loc_1800360A2
0x18003608e  cmp     [rbp+var_3E], 0
0x180036092  jz      short loc_1800360A2
0x180036094  mov     edx, [rbp+var_3C]
0x180036097  lea     rcx, [rbp+var_40]; this
0x18003609b  inc     edx; unsigned int
0x18003609d  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x1800360a2  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800360a6  lea     rdx, [rbp+arg_0]; unsigned __int8 **
0x1800360aa  lea     rcx, [rbp+var_20]; this
0x1800360ae  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1800360b3  mov     byte ptr [rbx+38h], 1
0x1800360b7  jmp     loc_180035FC6
0x1800360bc  xor     al, al
0x1800360be  mov     rbx, [rsp+70h+arg_8]
0x1800360c6  add     rsp, 70h
0x1800360ca  pop     r15
0x1800360cc  pop     r14
0x1800360ce  pop     r13
0x1800360d0  pop     r12
0x1800360d2  pop     rdi
0x1800360d3  pop     rsi
0x1800360d4  pop     rbp
0x1800360d5  retn
```
