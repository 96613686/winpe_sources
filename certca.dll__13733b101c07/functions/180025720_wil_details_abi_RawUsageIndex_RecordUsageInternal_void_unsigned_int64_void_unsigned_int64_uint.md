# wil::details_abi::RawUsageIndex::RecordUsageInternal(void *,unsigned __int64,void *,unsigned __int64,uint)

- ea: `0x180025720`
- end: `0x180025904`
- name: `?RecordUsageInternal@RawUsageIndex@details_abi@wil@@AEAA_NPEAX_K01I@Z`
- size: `484`
- prototype: `char __fastcall(wil::details_abi::RawUsageIndex *this, void *, size_t, void *, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180025634`

## callees

- `0x180023bc8`
- `0x180023ee4`
- `0x1800243f8`
- `0x1800251a0`
- `0x180025720`
- `0x180026004`
- `0x180026608`
- `0x180026850`

## import_xrefs

- `msvcrt!memmove_s` at `0x180025862`
- `msvcrt!memmove_s` at `0x180025862`

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
0x180025720  push    rbp
0x180025722  push    rbx
0x180025723  push    rsi
0x180025724  push    rdi
0x180025725  push    r12
0x180025727  push    r13
0x180025729  push    r14
0x18002572b  push    r15
0x18002572d  mov     rbp, rsp
0x180025730  sub     rsp, 78h
0x180025734  mov     rdi, [rcx+18h]
0x180025738  mov     r13, r9
0x18002573b  mov     r15, r8
0x18002573e  mov     r12, rdx
0x180025741  mov     rbx, rcx
0x180025744  test    rdi, rdi
0x180025747  jz      loc_1800258F1
0x18002574d  movzx   eax, word ptr [rcx+2]
0x180025751  add     rdi, 0Ah
0x180025755  mov     r8, [rcx+20h]
0x180025759  xorps   xmm0, xmm0
0x18002575c  mov     [rbp+var_48], ax
0x180025760  mov     al, [rcx+4]
0x180025763  mov     [rbp+var_46], al
0x180025766  xor     eax, eax
0x180025768  mov     [rbp+var_40], ax
0x18002576c  xor     r14b, r14b
0x18002576f  mov     [rbp+Source], rdi
0x180025773  mov     [rbp+var_44], 0
0x18002577a  movdqu  [rbp+var_38], xmm0
0x18002577f  jmp     short loc_1800257B9
0x180025781  mov     r8, r15; unsigned __int64
0x180025784  lea     rcx, [rbp+var_48]; this
0x180025788  mov     rdx, r12; void *
0x18002578b  call    ?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z; wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)
0x180025790  test    eax, eax
0x180025792  js      loc_1800258B4
0x180025798  mov     r8, [rbp+Source]; unsigned __int8 *
0x18002579c  lea     rdx, [rbp+var_48]; struct wil::details_abi::UsageIndexProperty *
0x1800257a0  jz      loc_180025884
0x1800257a6  mov     rcx, rbx; this
0x1800257a9  call    ?SkipValues@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAE@Z; wil::details_abi::RawUsageIndex::SkipValues(wil::details_abi::UsageIndexProperty &,uchar *)
0x1800257ae  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800257b2  mov     rdi, rax
0x1800257b5  mov     [rbp+Source], rax
0x1800257b9  lea     rdx, [rbp+Source]; unsigned __int8 **
0x1800257bd  lea     rcx, [rbp+var_48]; this
0x1800257c1  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800257c6  mov     sil, al
0x1800257c9  test    al, al
0x1800257cb  jnz     short loc_180025781
0x1800257cd  mov     rdi, [rbp+Source]
0x1800257d1  mov     [rbx+20h], rdi
0x1800257d5  xor     r8d, r8d
0x1800257d8  test    r14b, r14b
0x1800257db  jnz     short loc_1800257FD
0x1800257dd  lea     rcx, [rbp+var_48]; this
0x1800257e1  mov     [rbp+var_44], 1
0x1800257e8  mov     [rbp+var_40], r15w
0x1800257ed  mov     qword ptr [rbp+var_38], r8
0x1800257f1  mov     qword ptr [rbp+var_38+8], r12
0x1800257f5  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x1800257fa  mov     r8, rax
0x1800257fd  movzx   ecx, word ptr [rbx+6]
0x180025801  mov     eax, [rbp+arg_28]
0x180025804  mov     [rbp+var_28], cx
0x180025808  mov     cl, [rbx+8]
0x18002580b  mov     [rbp+var_24], eax
0x18002580e  mov     rax, [rbp+arg_20]
0x180025812  mov     [rbp+var_26], cl
0x180025815  lea     rcx, [rbp+var_28]; this
0x180025819  mov     [rbp+var_20], ax
0x18002581d  mov     [rbp+var_18], 0
0x180025825  mov     [rbp+var_10], r13
0x180025829  call    ?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ; wil::details_abi::UsageIndexProperty::GetSize(void)
0x18002582e  mov     rdx, [rbx+28h]
0x180025832  mov     r9, [rbx+20h]
0x180025836  mov     rcx, rdx
0x180025839  sub     rcx, r9
0x18002583c  lea     rsi, [rax+r8]
0x180025840  cmp     r9, rdx
0x180025843  sbb     rax, rax
0x180025846  and     rax, rcx
0x180025849  cmp     rax, rsi
0x18002584c  jb      loc_1800258F1
0x180025852  sub     rdx, rsi
0x180025855  lea     rcx, [rsi+rdi]; Destination
0x180025859  sub     rdx, rdi; DestinationSize
0x18002585c  sub     r9, rdi; SourceSize
0x18002585f  mov     r8, rdi; Source
0x180025862  call    cs:__imp_memmove_s
0x180025868  add     [rbx+20h], rsi
0x18002586c  test    r14b, r14b
0x18002586f  jnz     short loc_1800258C6
0x180025871  mov     r8, [rbx+20h]; unsigned __int8 *
0x180025875  lea     rdx, [rbp+Source]; unsigned __int8 **
0x180025879  lea     rcx, [rbp+var_48]; this
0x18002587d  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x180025882  jmp     short loc_1800258DA
0x180025884  mov     ecx, [rbp+arg_28]
0x180025887  mov     r9, r13; void *
0x18002588a  mov     [rsp+78h+var_50], ecx; unsigned int
0x18002588e  mov     rcx, [rbp+arg_20]
0x180025892  mov     [rsp+78h+var_58], rcx; unsigned __int64
0x180025897  mov     rcx, rbx; this
0x18002589a  call    ?FindInsertionPointOrIncrement@RawUsageIndex@details_abi@wil@@AEAAPEAEAEAUUsageIndexProperty@23@PEAEPEAX_KI@Z; wil::details_abi::RawUsageIndex::FindInsertionPointOrIncrement(wil::details_abi::UsageIndexProperty &,uchar *,void *,unsigned __int64,uint)
0x18002589f  mov     [rbp+Source], rax
0x1800258a3  mov     rdi, rax
0x1800258a6  test    rax, rax
0x1800258a9  jnz     short loc_1800258AF
0x1800258ab  mov     al, 1
0x1800258ad  jmp     short loc_1800258F3
0x1800258af  mov     r14b, 1
0x1800258b2  jmp     short loc_1800258B8
0x1800258b4  mov     [rbp+Source], rdi
0x1800258b8  test    sil, sil
0x1800258bb  jnz     loc_1800257D5
0x1800258c1  jmp     loc_1800257D1
0x1800258c6  cmp     [rbp+var_46], 0
0x1800258ca  jz      short loc_1800258DA
0x1800258cc  mov     edx, [rbp+var_44]
0x1800258cf  lea     rcx, [rbp+var_48]; this
0x1800258d3  inc     edx; unsigned int
0x1800258d5  call    ?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z; wil::details_abi::UsageIndexProperty::UpdateCount(uint)
0x1800258da  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800258de  lea     rdx, [rbp+Source]; unsigned __int8 **
0x1800258e2  lea     rcx, [rbp+var_28]; this
0x1800258e6  call    ?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)
0x1800258eb  mov     byte ptr [rbx+38h], 1
0x1800258ef  jmp     short loc_1800258AB
0x1800258f1  xor     al, al
0x1800258f3  add     rsp, 78h
0x1800258f7  pop     r15
0x1800258f9  pop     r14
0x1800258fb  pop     r13
0x1800258fd  pop     r12
0x1800258ff  pop     rdi
0x180025900  pop     rsi
0x180025901  pop     rbx
0x180025902  pop     rbp
0x180025903  retn
```
