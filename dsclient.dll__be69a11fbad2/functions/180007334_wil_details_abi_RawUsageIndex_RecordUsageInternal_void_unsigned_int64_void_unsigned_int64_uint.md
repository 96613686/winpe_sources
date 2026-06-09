# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180007334`
- end: `0x180007518`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `484`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180007240`

## callees

- `0x180005040`
- `0x180005438`
- `0x180005c80`
- `0x180006ca4`
- `0x180007334`
- `0x180007d34`
- `0x1800085ac`
- `0x1800089b8`

## import_xrefs

- `msvcrt!memmove_s` at `0x180007476`
- `msvcrt!memmove_s` at `0x180007476`

## pseudocode

```c
char __fastcall wil::details_abi::RawUsageIndex::RecordUsageInternal(
        wil::details_abi::RawUsageIndex *this,
        void *a2,
        size_t a3,
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
  const void *v24; // [rsp+30h] [rbp-48h] BYREF
  __int16 v25; // [rsp+38h] [rbp-40h]
  __int128 v26; // [rsp+40h] [rbp-38h]
  __int16 v27; // [rsp+50h] [rbp-28h] BYREF
  char v28; // [rsp+52h] [rbp-26h]
  unsigned int v29; // [rsp+54h] [rbp-24h]
  __int16 v30; // [rsp+58h] [rbp-20h]
  __int64 v31; // [rsp+60h] [rbp-18h]
  void *v32; // [rsp+68h] [rbp-10h]
  void *Source; // [rsp+C0h] [rbp+48h] BYREF

  v6 = *((_QWORD *)this + 3);
  if ( v6 )
  {
    v11 = (char *)(v6 + 10);
    v12 = (unsigned __int8 *)*((_QWORD *)this + 4);
    LOWORD(v24) = *((_WORD *)this + 1);
    BYTE2(v24) = *((_BYTE *)this + 4);
    v25 = 0;
    v13 = 0;
    Source = v11;
    HIDWORD(v24) = 0;
    v26 = 0;
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
      v14 = wil::details_abi::UsageIndexProperty::Compare(&v24, a2, a3);
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
      HIDWORD(v24) = 1;
      v25 = a3;
      *(_QWORD *)&v26 = 0;
      *((_QWORD *)&v26 + 1) = a2;
      wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v24);
    }
    v27 = *((_WORD *)this + 3);
    v17 = *((_BYTE *)this + 8);
    v29 = a6;
    v28 = v17;
    v30 = a5;
    v31 = 0;
    v32 = a4;
    Size = wil::details_abi::UsageIndexProperty::GetSize((wil::details_abi::UsageIndexProperty *)&v27);
    v19 = *((_QWORD *)this + 5);
    v20 = *((_QWORD *)this + 4);
    v22 = Size + v21;
    if ( ((v19 - v20) & -(__int64)(v20 < v19)) >= Size + v21 )
    {
      memmove_s(&v11[v22], v19 - v22 - (_QWORD)v11, v11, v20 - (_QWORD)v11);
      *((_QWORD *)this + 4) += v22;
      if ( v13 )
      {
        if ( BYTE2(v24) )
          wil::details_abi::UsageIndexProperty::UpdateCount(
            (wil::details_abi::UsageIndexProperty *)&v24,
            HIDWORD(v24) + 1);
      }
      else
      {
        wil::details_abi::UsageIndexProperty::Write(
          (wil::details_abi::UsageIndexProperty *)&v24,
          (unsigned __int8 **)&Source,
          *((unsigned __int8 **)this + 4));
      }
      wil::details_abi::UsageIndexProperty::Write(
        (wil::details_abi::UsageIndexProperty *)&v27,
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
0x180007334  push    rbp
0x180007336  push    rbx
0x180007337  push    rsi
0x180007338  push    rdi
0x180007339  push    r12
0x18000733b  push    r13
0x18000733d  push    r14
0x18000733f  push    r15
0x180007341  mov     rbp, rsp
0x180007344  sub     rsp, 78h
0x180007348  mov     rdi, [rcx+18h]
0x18000734c  mov     r13, r9
0x18000734f  mov     r15, r8
0x180007352  mov     r12, rdx
0x180007355  mov     rbx, rcx
0x180007358  test    rdi, rdi
0x18000735b  jz      loc_180007505
0x180007361  movzx   eax, word ptr [rcx+2]
0x180007365  add     rdi, 0Ah
0x180007369  mov     r8, [rcx+20h]
0x18000736d  xorps   xmm0, xmm0
0x180007370  mov     [rbp+var_48], ax
0x180007374  mov     al, [rcx+4]
0x180007377  mov     [rbp+var_46], al
0x18000737a  xor     eax, eax
0x18000737c  mov     [rbp+var_40], ax
0x180007380  xor     r14b, r14b
0x180007383  mov     [rbp+Source], rdi
0x180007387  mov     [rbp+var_44], 0
0x18000738e  movdqu  [rbp+var_38], xmm0
0x180007393  jmp     short loc_1800073CD
0x180007395  mov     r8, r15; unsigned __int64
0x180007398  lea     rcx, [rbp+var_48]; this
0x18000739c  mov     rdx, r12; void *
0x18000739f  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x1800073a4  test    eax, eax
0x1800073a6  js      loc_1800074C8
0x1800073ac  mov     r8, [rbp+Source]; unsigned __int8 *
0x1800073b0  lea     rdx, [rbp+var_48]; struct wil::details_abi::UsageIndexProperty *
0x1800073b4  jz      loc_180007498
0x1800073ba  mov     rcx, rbx; this
0x1800073bd  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x1800073c2  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800073c6  mov     rdi, rax
0x1800073c9  mov     [rbp+Source], rax
0x1800073cd  lea     rdx, [rbp+Source]; unsigned __int8 **
0x1800073d1  lea     rcx, [rbp+var_48]; this
0x1800073d5  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800073da  mov     sil, al
0x1800073dd  test    al, al
0x1800073df  jnz     short loc_180007395
0x1800073e1  mov     rdi, [rbp+Source]
0x1800073e5  mov     [rbx+20h], rdi
0x1800073e9  xor     r8d, r8d
0x1800073ec  test    r14b, r14b
0x1800073ef  jnz     short loc_180007411
0x1800073f1  lea     rcx, [rbp+var_48]; this
0x1800073f5  mov     [rbp+var_44], 1
0x1800073fc  mov     [rbp+var_40], r15w
0x180007401  mov     qword ptr [rbp+var_38], r8
0x180007405  mov     qword ptr [rbp+var_38+8], r12
0x180007409  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18000740e  mov     r8, rax
0x180007411  movzx   ecx, word ptr [rbx+6]
0x180007415  mov     eax, [rbp+arg_28]
0x180007418  mov     [rbp+var_28], cx
0x18000741c  mov     cl, [rbx+8]
0x18000741f  mov     [rbp+var_24], eax
0x180007422  mov     rax, [rbp+arg_20]
0x180007426  mov     [rbp+var_26], cl
0x180007429  lea     rcx, [rbp+var_28]; this
0x18000742d  mov     [rbp+var_20], ax
0x180007431  mov     [rbp+var_18], 0
0x180007439  mov     [rbp+var_10], r13
0x18000743d  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x180007442  mov     rdx, [rbx+28h]
0x180007446  mov     r9, [rbx+20h]
0x18000744a  mov     rcx, rdx
0x18000744d  sub     rcx, r9
0x180007450  lea     rsi, [rax+r8]
0x180007454  cmp     r9, rdx
0x180007457  sbb     rax, rax
0x18000745a  and     rax, rcx
0x18000745d  cmp     rax, rsi
0x180007460  jb      loc_180007505
0x180007466  sub     rdx, rsi
0x180007469  lea     rcx, [rsi+rdi]; Destination
0x18000746d  sub     rdx, rdi; DestinationSize
0x180007470  sub     r9, rdi; SourceSize
0x180007473  mov     r8, rdi; Source
0x180007476  call    cs:__imp_memmove_s
0x18000747c  add     [rbx+20h], rsi
0x180007480  test    r14b, r14b
0x180007483  jnz     short loc_1800074DA
0x180007485  mov     r8, [rbx+20h]; unsigned __int8 *
0x180007489  lea     rdx, [rbp+Source]; unsigned __int8 **
0x18000748d  lea     rcx, [rbp+var_48]; this
0x180007491  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180007496  jmp     short loc_1800074EE
0x180007498  mov     ecx, [rbp+arg_28]
0x18000749b  mov     r9, r13; void *
0x18000749e  mov     [rsp+78h+var_50], ecx; unsigned int
0x1800074a2  mov     rcx, [rbp+arg_20]
0x1800074a6  mov     [rsp+78h+var_58], rcx; unsigned __int64
0x1800074ab  mov     rcx, rbx; this
0x1800074ae  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x1800074b3  mov     [rbp+Source], rax
0x1800074b7  mov     rdi, rax
0x1800074ba  test    rax, rax
0x1800074bd  jnz     short loc_1800074C3
0x1800074bf  mov     al, 1
0x1800074c1  jmp     short loc_180007507
0x1800074c3  mov     r14b, 1
0x1800074c6  jmp     short loc_1800074CC
0x1800074c8  mov     [rbp+Source], rdi
0x1800074cc  test    sil, sil
0x1800074cf  jnz     loc_1800073E9
0x1800074d5  jmp     loc_1800073E5
0x1800074da  cmp     [rbp+var_46], 0
0x1800074de  jz      short loc_1800074EE
0x1800074e0  mov     edx, [rbp+var_44]
0x1800074e3  lea     rcx, [rbp+var_48]; this
0x1800074e7  inc     edx; unsigned int
0x1800074e9  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x1800074ee  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800074f2  lea     rdx, [rbp+Source]; unsigned __int8 **
0x1800074f6  lea     rcx, [rbp+var_28]; this
0x1800074fa  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1800074ff  mov     byte ptr [rbx+38h], 1
0x180007503  jmp     short loc_1800074BF
0x180007505  xor     al, al
0x180007507  add     rsp, 78h
0x18000750b  pop     r15
0x18000750d  pop     r14
0x18000750f  pop     r13
0x180007511  pop     r12
0x180007513  pop     rdi
0x180007514  pop     rsi
0x180007515  pop     rbx
0x180007516  pop     rbp
0x180007517  retn
```
