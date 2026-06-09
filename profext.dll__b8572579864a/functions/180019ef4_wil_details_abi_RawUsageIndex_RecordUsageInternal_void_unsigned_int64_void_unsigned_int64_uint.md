# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180019ef4`
- end: `0x18001a0df`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `491`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *__hidden this, void *, unsigned __int64, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180019e00`

## callees

- `0x18001444c`
- `0x180016df8`
- `0x180018ce8`
- `0x180019880`
- `0x180019ef4`
- `0x18001ada4`
- `0x18001b1cc`
- `0x18001b654`

## import_xrefs

- `msvcrt!memmove_s` at `0x18001a036`
- `msvcrt!memmove_s` at `0x18001a036`

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
0x180019ef4  push    rbp
0x180019ef6  push    rbx
0x180019ef7  push    rsi
0x180019ef8  push    rdi
0x180019ef9  push    r12
0x180019efb  push    r13
0x180019efd  push    r14
0x180019eff  push    r15
0x180019f01  mov     rbp, rsp
0x180019f04  sub     rsp, 78h
0x180019f08  mov     rdi, [rcx+18h]
0x180019f0c  mov     r13, r9
0x180019f0f  mov     r15, r8
0x180019f12  mov     r12, rdx
0x180019f15  mov     rbx, rcx
0x180019f18  test    rdi, rdi
0x180019f1b  jz      loc_18001A0CB
0x180019f21  movzx   eax, word ptr [rcx+2]
0x180019f25  add     rdi, 0Ah
0x180019f29  mov     r8, [rcx+20h]
0x180019f2d  xorps   xmm0, xmm0
0x180019f30  mov     [rbp+var_48], ax
0x180019f34  mov     al, [rcx+4]
0x180019f37  mov     [rbp+var_46], al
0x180019f3a  xor     eax, eax
0x180019f3c  mov     [rbp+var_40], ax
0x180019f40  xor     r14b, r14b
0x180019f43  mov     [rbp+Source], rdi
0x180019f47  mov     [rbp+var_44], 0
0x180019f4e  movdqu  [rbp+var_38], xmm0
0x180019f53  jmp     short loc_180019F8D
0x180019f55  mov     r8, r15; unsigned __int64
0x180019f58  lea     rcx, [rbp+var_48]; this
0x180019f5c  mov     rdx, r12; void *
0x180019f5f  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x180019f64  test    eax, eax
0x180019f66  js      loc_18001A08E
0x180019f6c  mov     r8, [rbp+Source]; unsigned __int8 *
0x180019f70  lea     rdx, [rbp+var_48]; struct wil::details_abi::UsageIndexProperty *
0x180019f74  jz      loc_18001A05E
0x180019f7a  mov     rcx, rbx; this
0x180019f7d  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x180019f82  mov     r8, [rbx+20h]; unsigned __int8 *
0x180019f86  mov     rdi, rax
0x180019f89  mov     [rbp+Source], rax
0x180019f8d  lea     rdx, [rbp+Source]; unsigned __int8 **
0x180019f91  lea     rcx, [rbp+var_48]; this
0x180019f95  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180019f9a  mov     sil, al
0x180019f9d  test    al, al
0x180019f9f  jnz     short loc_180019F55
0x180019fa1  mov     rdi, [rbp+Source]
0x180019fa5  mov     [rbx+20h], rdi
0x180019fa9  xor     r8d, r8d
0x180019fac  test    r14b, r14b
0x180019faf  jnz     short loc_180019FD1
0x180019fb1  lea     rcx, [rbp+var_48]; this
0x180019fb5  mov     [rbp+var_44], 1
0x180019fbc  mov     [rbp+var_40], r15w
0x180019fc1  mov     qword ptr [rbp+var_38], r8
0x180019fc5  mov     qword ptr [rbp+var_38+8], r12
0x180019fc9  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180019fce  mov     r8, rax
0x180019fd1  movzx   ecx, word ptr [rbx+6]
0x180019fd5  mov     eax, [rbp+arg_28]
0x180019fd8  mov     [rbp+var_28], cx
0x180019fdc  mov     cl, [rbx+8]
0x180019fdf  mov     [rbp+var_24], eax
0x180019fe2  mov     rax, [rbp+arg_20]
0x180019fe6  mov     [rbp+var_26], cl
0x180019fe9  lea     rcx, [rbp+var_28]; this
0x180019fed  mov     [rbp+var_20], ax
0x180019ff1  mov     [rbp+var_18], 0
0x180019ff9  mov     [rbp+var_10], r13
0x180019ffd  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18001a002  mov     rdx, [rbx+28h]
0x18001a006  mov     r9, [rbx+20h]
0x18001a00a  mov     rcx, rdx
0x18001a00d  sub     rcx, r9
0x18001a010  lea     rsi, [rax+r8]
0x18001a014  cmp     r9, rdx
0x18001a017  sbb     rax, rax
0x18001a01a  and     rax, rcx
0x18001a01d  cmp     rax, rsi
0x18001a020  jb      loc_18001A0CB
0x18001a026  sub     rdx, rsi
0x18001a029  lea     rcx, [rsi+rdi]; Destination
0x18001a02d  sub     rdx, rdi; DestinationSize
0x18001a030  sub     r9, rdi; SourceSize
0x18001a033  mov     r8, rdi; Source
0x18001a036  call    cs:__imp_memmove_s
0x18001a03d  nop     dword ptr [rax+rax+00h]
0x18001a042  add     [rbx+20h], rsi
0x18001a046  test    r14b, r14b
0x18001a049  jnz     short loc_18001A0A0
0x18001a04b  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001a04f  lea     rdx, [rbp+Source]; unsigned __int8 **
0x18001a053  lea     rcx, [rbp+var_48]; this
0x18001a057  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18001a05c  jmp     short loc_18001A0B4
0x18001a05e  mov     ecx, [rbp+arg_28]
0x18001a061  mov     r9, r13; void *
0x18001a064  mov     [rsp+78h+var_50], ecx; unsigned int
0x18001a068  mov     rcx, [rbp+arg_20]
0x18001a06c  mov     [rsp+78h+var_58], rcx; unsigned __int64
0x18001a071  mov     rcx, rbx; this
0x18001a074  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18001a079  mov     [rbp+Source], rax
0x18001a07d  mov     rdi, rax
0x18001a080  test    rax, rax
0x18001a083  jnz     short loc_18001A089
0x18001a085  mov     al, 1
0x18001a087  jmp     short loc_18001A0CD
0x18001a089  mov     r14b, 1
0x18001a08c  jmp     short loc_18001A092
0x18001a08e  mov     [rbp+Source], rdi
0x18001a092  test    sil, sil
0x18001a095  jnz     loc_180019FA9
0x18001a09b  jmp     loc_180019FA5
0x18001a0a0  cmp     [rbp+var_46], 0
0x18001a0a4  jz      short loc_18001A0B4
0x18001a0a6  mov     edx, [rbp+var_44]
0x18001a0a9  lea     rcx, [rbp+var_48]; this
0x18001a0ad  inc     edx; unsigned int
0x18001a0af  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x18001a0b4  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001a0b8  lea     rdx, [rbp+Source]; unsigned __int8 **
0x18001a0bc  lea     rcx, [rbp+var_28]; this
0x18001a0c0  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x18001a0c5  mov     byte ptr [rbx+38h], 1
0x18001a0c9  jmp     short loc_18001A085
0x18001a0cb  xor     al, al
0x18001a0cd  add     rsp, 78h
0x18001a0d1  pop     r15
0x18001a0d3  pop     r14
0x18001a0d5  pop     r13
0x18001a0d7  pop     r12
0x18001a0d9  pop     rdi
0x18001a0da  pop     rsi
0x18001a0db  pop     rbx
0x18001a0dc  pop     rbp
0x18001a0dd  retn
```
